---
title: Microsoft 365 for business 準備 Office 用戶端部署
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 瞭解如何在 Windows 10 電腦上自動安裝32位 Office 應用程式，並將其保持更新。
ms.openlocfilehash: 6f3a80be9729a3818607c0f42e2cc7ece66a07ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401315"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="aee42-103">Microsoft 365 for business 準備 Office 用戶端部署</span><span class="sxs-lookup"><span data-stu-id="aee42-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="aee42-104">準備將 Office App 自動安裝到用戶端電腦</span><span class="sxs-lookup"><span data-stu-id="aee42-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="aee42-105">您可以使用 Microsoft 365 for business，在 Windows 10 電腦上自動安裝32位 Office 應用程式，並將更新維持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="aee42-105">You can use Microsoft 365 for business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="aee42-106">如果使用者的電腦在 Windows 10 商務版上，則自動安裝效果最好，而且：</span><span class="sxs-lookup"><span data-stu-id="aee42-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="aee42-107">沒有現有的 Office 傳統型應用程式 (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive)。</span><span class="sxs-lookup"><span data-stu-id="aee42-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="aee42-108">或</span><span class="sxs-lookup"><span data-stu-id="aee42-108">or</span></span>
    
- <span data-ttu-id="aee42-109">已安裝現有版本的隨選即用 Office。</span><span class="sxs-lookup"><span data-stu-id="aee42-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="aee42-110">若要判斷您是否有 office 的 Click-to-Run 版本，請在任何 Office 應用程式**中，移至** \> [檔案**帳戶**（Outlook 中的**Office 帳戶**）]。</span><span class="sxs-lookup"><span data-stu-id="aee42-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="aee42-111">如果您看到如下圖所示的**Office 更新**，則是使用 Click-to-Run 執行安裝。</span><span class="sxs-lookup"><span data-stu-id="aee42-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="aee42-113">**享受此功能的好處**</span><span class="sxs-lookup"><span data-stu-id="aee42-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="aee42-114">電腦符合下列情況的使用者：</span><span class="sxs-lookup"><span data-stu-id="aee42-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="aee42-115">**具有**Windows 10 商務版使用者授權、使用中 Microsoft 365 for Business 授權、Windows 10 創意者更新，以及加入 Azure active Directory。</span><span class="sxs-lookup"><span data-stu-id="aee42-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="aee42-116">**沒有64位**的 Office app （例如： Word、Excel、PowerPoint）。</span><span class="sxs-lookup"><span data-stu-id="aee42-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="aee42-117">如果需要64位的 Office app，這項功能不是很好的，因為不支援從 Microsoft 365 for business 管理主控台觸發64位的 2016 Click-to-Run 版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="aee42-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="aee42-118">**沒有任何 2016** Windows INSTALLER （MSI）獨立應用程式（例如 Visio 或 Project）。</span><span class="sxs-lookup"><span data-stu-id="aee42-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="aee42-119">Microsoft 365 for business 將 Office 升級至 Office 2016 的 Click-to-Run 版本，但無法搭配 Office 2016 MSI 獨立應用程式使用。</span><span class="sxs-lookup"><span data-stu-id="aee42-119">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="aee42-120">下表顯示使用者/系統管理員可能需要採取的動作，視其開始狀態而定，若要從 Microsoft 365 for business 系統管理主控台取得成功的 Office 部署32位 Click-to-Run 版本。</span><span class="sxs-lookup"><span data-stu-id="aee42-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="aee42-121">**啟動 Office 安裝狀態**</span><span class="sxs-lookup"><span data-stu-id="aee42-121">**Starting Office install status**</span></span>|<span data-ttu-id="aee42-122">**Microsoft 365 for business Office 安裝前所要採取的動作**</span><span class="sxs-lookup"><span data-stu-id="aee42-122">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="aee42-123">**結束狀態**</span><span class="sxs-lookup"><span data-stu-id="aee42-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aee42-124">未安裝任何 Office 套件</span><span class="sxs-lookup"><span data-stu-id="aee42-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="aee42-125">無</span><span class="sxs-lookup"><span data-stu-id="aee42-125">None</span></span>  <br/> |<span data-ttu-id="aee42-126">使用 Click-to-Run 安裝 Office 2016 32 位</span><span class="sxs-lookup"><span data-stu-id="aee42-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="aee42-127">現有的隨選即用 32 位元版本的 Office (2016 或更舊版本)，且沒有獨立版本 App</span><span class="sxs-lookup"><span data-stu-id="aee42-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="aee42-128">無</span><span class="sxs-lookup"><span data-stu-id="aee42-128">None</span></span>  <br/> |<span data-ttu-id="aee42-129">視需要升級至最新的32位 Click-to-Run 版本的 Office 2016**\***</span><span class="sxs-lookup"><span data-stu-id="aee42-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="aee42-130">現有 Click-to-Run 32 位版本的 Office，以及 Click-to-Run 32 位或64位獨立 Office 應用程式（例如 Visio、Project）</span><span class="sxs-lookup"><span data-stu-id="aee42-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="aee42-131">無</span><span class="sxs-lookup"><span data-stu-id="aee42-131">None</span></span>  <br/> |<span data-ttu-id="aee42-132">獨立應用程式不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="aee42-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="aee42-133">套件已升級到隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="aee42-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="aee42-134">現有的隨選即用 32 位元版本的 Office，以及任何 32 位元或 64 位元 (2016 除外) MSI 獨立版本 Office App</span><span class="sxs-lookup"><span data-stu-id="aee42-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="aee42-135">無</span><span class="sxs-lookup"><span data-stu-id="aee42-135">None</span></span>  <br/> |<span data-ttu-id="aee42-136">獨立應用程式不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="aee42-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="aee42-137">套件已升級到隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="aee42-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="aee42-138">任何現有的隨選即用 64 位元版本的 Office</span><span class="sxs-lookup"><span data-stu-id="aee42-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="aee42-139">卸載64位 Office 應用程式（如果有的話）以32位 Office app 取代它們</span><span class="sxs-lookup"><span data-stu-id="aee42-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="aee42-140">如果 Office 64 位元 App 遭到移除，則會安裝隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="aee42-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="aee42-141">包含或不包含獨立版本 App 之現有的 MSI Office 2016 安裝</span><span class="sxs-lookup"><span data-stu-id="aee42-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="aee42-142">解除安裝 MSI Office 2016。</span><span class="sxs-lookup"><span data-stu-id="aee42-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="aee42-p106">已安裝隨選即用 32 位元版本的 Office 2016。不會變更獨立版本 App</span><span class="sxs-lookup"><span data-stu-id="aee42-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="aee42-145">現有的 MSI Office 2013 (或更舊版本) 安裝和/或獨立版本 Office App</span><span class="sxs-lookup"><span data-stu-id="aee42-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="aee42-146">無</span><span class="sxs-lookup"><span data-stu-id="aee42-146">None</span></span>  <br/> |<span data-ttu-id="aee42-147">隨選即用 32 位元版本的 Office 2016 與既有的 MSI Office 安裝 (和獨立版本 App) 並存</span><span class="sxs-lookup"><span data-stu-id="aee42-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="aee42-148">**（ \* ）注意：** 由於已知的錯誤，不會升級為 Click-to-Run 32 位版本的 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="aee42-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="aee42-149">修正程式正在進行中。</span><span class="sxs-lookup"><span data-stu-id="aee42-149">A fix is in progress.</span></span> 
  
