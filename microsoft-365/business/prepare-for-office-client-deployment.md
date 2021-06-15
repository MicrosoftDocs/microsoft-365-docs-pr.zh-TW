---
title: 為商務 Microsoft 365 準備 Office 用戶端部署
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 瞭解如何在 Windows 10 電腦上自動安裝32位 Office 應用程式，並將它們更新。
ms.openlocfilehash: 843be426d817da1173769b3b66dc4c054179f0fd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924220"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="339cb-103">為商務 Microsoft 365 準備 Office 用戶端部署</span><span class="sxs-lookup"><span data-stu-id="339cb-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="339cb-104">本文適用于 Microsoft 365 商務進階版。</span><span class="sxs-lookup"><span data-stu-id="339cb-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="339cb-105">準備將 Office App 自動安裝到用戶端電腦</span><span class="sxs-lookup"><span data-stu-id="339cb-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="339cb-106">您可以使用 Microsoft 365 商務進階版在 Windows 10 電腦上自動安裝32位 Office 應用程式，並將更新維持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="339cb-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="339cb-107">如果使用者的電腦位於 Windows 10 商務版，則自動安裝效果最好，且：</span><span class="sxs-lookup"><span data-stu-id="339cb-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="339cb-108">沒有現有的 Office 傳統型應用程式 (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive)。</span><span class="sxs-lookup"><span data-stu-id="339cb-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="339cb-109">或</span><span class="sxs-lookup"><span data-stu-id="339cb-109">or</span></span>
    
- <span data-ttu-id="339cb-110">已安裝現有版本的隨選即用 Office。</span><span class="sxs-lookup"><span data-stu-id="339cb-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="339cb-111">若要判斷您是否有 Office 的 Click-to-Run 版本，請在任何 Office 應用程式移 **至檔案** \> **帳戶** ( Office Outlook 中的 **帳戶**。</span><span class="sxs-lookup"><span data-stu-id="339cb-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="339cb-112">如果您看到 **Office 的更新** 如下圖所示，則是使用 Click-to-Run 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="339cb-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="339cb-114">**利用這項功能神秘好處**</span><span class="sxs-lookup"><span data-stu-id="339cb-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="339cb-115">電腦符合下列情況的使用者：</span><span class="sxs-lookup"><span data-stu-id="339cb-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="339cb-116">**具有** Windows 10 商務版使用者授權、商務用 Microsoft 365 商務版授權、Windows 10 建立者更新，以及加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="339cb-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="339cb-117">Office 應用程式 **沒有64位** (範例： Word、Excel PowerPoint) 。</span><span class="sxs-lookup"><span data-stu-id="339cb-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="339cb-118">如果需要64位 Office 應用程式，則這項功能不是很好的，因為不支援從 business administration console 的 Microsoft 365 觸發64位 2016 Click-to-Run 版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="339cb-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="339cb-119">**沒有任何 2016** Windows 安裝程式 (MSI) 獨立應用程式 (例如 Visio 或 Project) 。</span><span class="sxs-lookup"><span data-stu-id="339cb-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="339cb-120">Microsoft 365 以進行商務升級 Office Click-to-Run 版本的 Office 2016，而且無法使用 Office 2016 MSI 獨立應用程式。</span><span class="sxs-lookup"><span data-stu-id="339cb-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="339cb-121">下表顯示使用者/系統管理員可能需要採取的動作，視其開始狀態而定，若要從 business admin console Microsoft 365 取得32成功的 Office 部署 Click-to-Run 版本。</span><span class="sxs-lookup"><span data-stu-id="339cb-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span><br/>


|<span data-ttu-id="339cb-122">啟動 Office 安裝狀態</span><span class="sxs-lookup"><span data-stu-id="339cb-122">Starting Office install status</span></span>|<span data-ttu-id="339cb-123">在 Microsoft 365 商務 Office 安裝之前採取的動作</span><span class="sxs-lookup"><span data-stu-id="339cb-123">Action to take before Microsoft 365 for business Office install</span></span>|<span data-ttu-id="339cb-124">結束狀態</span><span class="sxs-lookup"><span data-stu-id="339cb-124">End state</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="339cb-125">未安裝任何 Office 套件</span><span class="sxs-lookup"><span data-stu-id="339cb-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="339cb-126">無</span><span class="sxs-lookup"><span data-stu-id="339cb-126">None</span></span>  <br/> |<span data-ttu-id="339cb-127">使用 Click-to-Run 安裝 Office 2016 32 位</span><span class="sxs-lookup"><span data-stu-id="339cb-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="339cb-128">現有的隨選即用 32 位元版本的 Office (2016 或更舊版本)，且沒有獨立版本 App</span><span class="sxs-lookup"><span data-stu-id="339cb-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="339cb-129">無</span><span class="sxs-lookup"><span data-stu-id="339cb-129">None</span></span>  <br/> |<span data-ttu-id="339cb-130">視需要升級為 Office 2016 的最新32位 Click-to-Run 版本 **\***</span><span class="sxs-lookup"><span data-stu-id="339cb-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="339cb-131">現有 Click-to-Run 32 位版本的 Office 和 Click-to-Run 32 位或64位獨立 Office 應用程式 (例如 Visio、Project) </span><span class="sxs-lookup"><span data-stu-id="339cb-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="339cb-132">無</span><span class="sxs-lookup"><span data-stu-id="339cb-132">None</span></span>  <br/> |<span data-ttu-id="339cb-133">獨立應用程式不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="339cb-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="339cb-134">套件已升級到隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="339cb-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="339cb-135">現有的隨選即用 32 位元版本的 Office，以及任何 32 位元或 64 位元 (2016 除外) MSI 獨立版本 Office App</span><span class="sxs-lookup"><span data-stu-id="339cb-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="339cb-136">無</span><span class="sxs-lookup"><span data-stu-id="339cb-136">None</span></span>  <br/> |<span data-ttu-id="339cb-137">獨立應用程式不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="339cb-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="339cb-138">套件已升級到隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="339cb-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="339cb-139">任何現有的隨選即用 64 位元版本的 Office</span><span class="sxs-lookup"><span data-stu-id="339cb-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="339cb-140">卸載64位 Office 應用程式（如果有的話）以32位 Office 應用程式來取代它們</span><span class="sxs-lookup"><span data-stu-id="339cb-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="339cb-141">如果 Office 64 位元 App 遭到移除，則會安裝隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="339cb-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="339cb-142">包含或不包含獨立版本 App 之現有的 MSI Office 2016 安裝</span><span class="sxs-lookup"><span data-stu-id="339cb-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="339cb-143">解除安裝 MSI Office 2016。</span><span class="sxs-lookup"><span data-stu-id="339cb-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="339cb-p106">已安裝隨選即用 32 位元版本的 Office 2016。不會變更獨立版本 App</span><span class="sxs-lookup"><span data-stu-id="339cb-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="339cb-146">現有的 MSI Office 2013 (或更舊版本) 安裝和/或獨立版本 Office App</span><span class="sxs-lookup"><span data-stu-id="339cb-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="339cb-147">無</span><span class="sxs-lookup"><span data-stu-id="339cb-147">None</span></span>  <br/> |<span data-ttu-id="339cb-148">隨選即用 32 位元版本的 Office 2016 與既有的 MSI Office 安裝 (和獨立版本 App) 並存</span><span class="sxs-lookup"><span data-stu-id="339cb-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="339cb-149">**(\*) 附注：** 由於已知的錯誤，不會升級為 Office 2016 的 Click-to-Run 32 位版本。</span><span class="sxs-lookup"><span data-stu-id="339cb-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="339cb-150">修正程式正在進行中。</span><span class="sxs-lookup"><span data-stu-id="339cb-150">A fix is in progress.</span></span> 
  
