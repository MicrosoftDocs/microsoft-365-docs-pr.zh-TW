---
title: 透過 Microsoft 365 商務版準備 Office 用戶端部署
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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 了解如何自動在 Windows 10 電腦上安裝 32 位元 Office app，並讓這些更新。
ms.openlocfilehash: 09857ddeb28e953da07979045a65f6b91925aeaf
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640762"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="19ffd-103">透過 Microsoft 365 商務版準備 Office 用戶端部署</span><span class="sxs-lookup"><span data-stu-id="19ffd-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="19ffd-104">準備將 Office App 自動安裝到用戶端電腦</span><span class="sxs-lookup"><span data-stu-id="19ffd-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="19ffd-105">您可以使用 Microsoft 365 商務版，自動在 Windows 10 電腦上安裝 32 位元 Office app，並維持更新。</span><span class="sxs-lookup"><span data-stu-id="19ffd-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="19ffd-106">自動安裝適合如果使用者的電腦在 Windows 10 商務版和：</span><span class="sxs-lookup"><span data-stu-id="19ffd-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="19ffd-107">沒有現有的 Office 傳統型應用程式 (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive)。</span><span class="sxs-lookup"><span data-stu-id="19ffd-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="19ffd-108">或</span><span class="sxs-lookup"><span data-stu-id="19ffd-108">or</span></span>
    
- <span data-ttu-id="19ffd-109">已安裝現有版本的隨選即用 Office。</span><span class="sxs-lookup"><span data-stu-id="19ffd-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="19ffd-110">若要判斷是否有按一下-隨選即用版本的 Office，在任何 Office 應用程式移至 [**檔案** \> **帳戶**（在 Outlook 中的**Office 帳戶**）。</span><span class="sxs-lookup"><span data-stu-id="19ffd-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="19ffd-111">如果您看到**Office 更新**，如下圖所示，安裝已完成使用 Click-隨選即用。</span><span class="sxs-lookup"><span data-stu-id="19ffd-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="19ffd-113">**誰福利由這項功能**</span><span class="sxs-lookup"><span data-stu-id="19ffd-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="19ffd-114">電腦符合下列情況的使用者：</span><span class="sxs-lookup"><span data-stu-id="19ffd-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="19ffd-115">**具有**Windows 10 商務版使用者授權，作用中的 Microsoft 365 商務版授權，Windows 10 Creators Update，且已加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="19ffd-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="19ffd-116">**沒有**64 位元 Office app (範例： Word、 Excel、 PowerPoint)。</span><span class="sxs-lookup"><span data-stu-id="19ffd-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="19ffd-117">如果 64 位元 Office app 是必要的則這項功能不適合，因為不支援觸發 64 位元 2016年按一下-隨選即用版本的 Office 從 Microsoft 365 商務版系統管理主控台。</span><span class="sxs-lookup"><span data-stu-id="19ffd-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="19ffd-118">**沒有**任何 2016 Windows Installer (MSI) 獨立應用程式 （例如 Visio 或 Project）。</span><span class="sxs-lookup"><span data-stu-id="19ffd-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="19ffd-119">Microsoft 365 商務版 Office 升級為按一下-隨選即用版本的 Office 2016 及，不適用於 Office 2016 MSI 獨立版本 app。</span><span class="sxs-lookup"><span data-stu-id="19ffd-119">Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="19ffd-120">下表顯示哪些巨集指令的使用者/系統管理員可能需要執行，根據其開頭的狀態，成功的 32 位元按一下-隨選即用版本的 Office 部署 Microsoft 365 商務版系統管理主控台。</span><span class="sxs-lookup"><span data-stu-id="19ffd-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="19ffd-121">**啟動 Office 安裝狀態**</span><span class="sxs-lookup"><span data-stu-id="19ffd-121">**Starting Office install status**</span></span>|<span data-ttu-id="19ffd-122">**在安裝 Microsoft 365 商務版 Office 之前需採取的動作**</span><span class="sxs-lookup"><span data-stu-id="19ffd-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="19ffd-123">**結束狀態**</span><span class="sxs-lookup"><span data-stu-id="19ffd-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="19ffd-124">未安裝任何 Office 套件</span><span class="sxs-lookup"><span data-stu-id="19ffd-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="19ffd-125">無</span><span class="sxs-lookup"><span data-stu-id="19ffd-125">None</span></span>  <br/> |<span data-ttu-id="19ffd-126">藉由按一下 [-隨選即用安裝 office 2016 32年位元</span><span class="sxs-lookup"><span data-stu-id="19ffd-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="19ffd-127">現有的隨選即用 32 位元版本的 Office (2016 或更舊版本)，且沒有獨立版本 App</span><span class="sxs-lookup"><span data-stu-id="19ffd-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="19ffd-128">無</span><span class="sxs-lookup"><span data-stu-id="19ffd-128">None</span></span>  <br/> |<span data-ttu-id="19ffd-129">視需要升級至最新的 32 位元按一下-隨選即用版本的 Office 2016，**\***</span><span class="sxs-lookup"><span data-stu-id="19ffd-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="19ffd-130">現有的按一下 [若要執行 32 位元版本的 Office 並按一下 [若要執行 32 位元或 64 位元獨立 Office 應用程式 （例如，Visio、 Project）</span><span class="sxs-lookup"><span data-stu-id="19ffd-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="19ffd-131">無</span><span class="sxs-lookup"><span data-stu-id="19ffd-131">None</span></span>  <br/> |<span data-ttu-id="19ffd-132">獨立版本 app 不受影響。</span><span class="sxs-lookup"><span data-stu-id="19ffd-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="19ffd-133">套件已升級到隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="19ffd-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="19ffd-134">現有的隨選即用 32 位元版本的 Office，以及任何 32 位元或 64 位元 (2016 除外) MSI 獨立版本 Office App</span><span class="sxs-lookup"><span data-stu-id="19ffd-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="19ffd-135">無</span><span class="sxs-lookup"><span data-stu-id="19ffd-135">None</span></span>  <br/> |<span data-ttu-id="19ffd-136">獨立版本 app 不受影響。</span><span class="sxs-lookup"><span data-stu-id="19ffd-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="19ffd-137">套件已升級到隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="19ffd-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="19ffd-138">任何現有的隨選即用 64 位元版本的 Office</span><span class="sxs-lookup"><span data-stu-id="19ffd-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="19ffd-139">如果是 [確定] 以將它取代為 32 位元 Office 應用程式解除安裝 64 位元 Office 應用程式]，</span><span class="sxs-lookup"><span data-stu-id="19ffd-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="19ffd-140">如果 Office 64 位元 App 遭到移除，則會安裝隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="19ffd-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="19ffd-141">包含或不包含獨立版本 App 之現有的 MSI Office 2016 安裝</span><span class="sxs-lookup"><span data-stu-id="19ffd-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="19ffd-142">解除安裝 MSI Office 2016。</span><span class="sxs-lookup"><span data-stu-id="19ffd-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="19ffd-p106">已安裝隨選即用 32 位元版本的 Office 2016。不會變更獨立版本 App</span><span class="sxs-lookup"><span data-stu-id="19ffd-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="19ffd-145">現有的 MSI Office 2013 (或更舊版本) 安裝和/或獨立版本 Office App</span><span class="sxs-lookup"><span data-stu-id="19ffd-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="19ffd-146">無</span><span class="sxs-lookup"><span data-stu-id="19ffd-146">None</span></span>  <br/> |<span data-ttu-id="19ffd-147">隨選即用 32 位元版本的 Office 2016 與既有的 MSI Office 安裝 (和獨立版本 App) 並存</span><span class="sxs-lookup"><span data-stu-id="19ffd-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="19ffd-148">**(\*) 附註：** 不會升級到按一下 [若要執行 32 位元版本的 Office 2016 由於已知的錯誤。</span><span class="sxs-lookup"><span data-stu-id="19ffd-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="19ffd-149">修正正在進行中。</span><span class="sxs-lookup"><span data-stu-id="19ffd-149">A fix is in progress.</span></span> 
  