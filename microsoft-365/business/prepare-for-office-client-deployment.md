---
title: 透過 Microsoft 365 商務版準備 Office 用戶端部署
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 了解如何自動安裝 32 位元的 Office 應用程式到 Windows 10 電腦並保留加以更新。
ms.openlocfilehash: 16a8230d60157f1c6731ac639d89533b05aa3afe
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866116"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="35c25-103">透過 Microsoft 365 商務版準備 Office 用戶端部署</span><span class="sxs-lookup"><span data-stu-id="35c25-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="35c25-104">準備將 Office App 自動安裝到用戶端電腦</span><span class="sxs-lookup"><span data-stu-id="35c25-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="35c25-105">您可以使用 Microsoft 365 商務版將 32 位元的 Office App 自動安裝到 Windows 10 電腦，並讓這些 App 保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="35c25-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="35c25-106">此功能適用於搭載 Windows 10 商務版且符合以下情況的電腦：</span><span class="sxs-lookup"><span data-stu-id="35c25-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="35c25-107">沒有現有的 Office 傳統型應用程式 (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive)。</span><span class="sxs-lookup"><span data-stu-id="35c25-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="35c25-108">或</span><span class="sxs-lookup"><span data-stu-id="35c25-108">or</span></span>
    
- <span data-ttu-id="35c25-109">已安裝現有版本的隨選即用 Office。</span><span class="sxs-lookup"><span data-stu-id="35c25-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="35c25-p101">若要判斷是否有 Office，按一下 [-隨選即用版本的任何 Office 應用程式移至 [**檔案** \> **帳戶**（在 Outlook 中的**Office 帳戶**）。如果您看到 Office 更新，如下圖所示，使用 Click-隨選即用來已完成安裝。</span><span class="sxs-lookup"><span data-stu-id="35c25-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="35c25-113">**誰會藉由這項功能獲益**</span><span class="sxs-lookup"><span data-stu-id="35c25-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="35c25-114">電腦符合下列情況的使用者：</span><span class="sxs-lookup"><span data-stu-id="35c25-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="35c25-115">**具有**一個 Windows 10 商務使用者的授權，作用中的 Microsoft 365 商務授權、 Windows 10 建立者更新，並會加入至 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="35c25-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="35c25-p102">**都不會有**64 位元 Office 應用程式 (範例： Word、 Excel、 Powerpoint)。如果 64 位元 Office 應用程式所需的則此功能不是很好的調整由於不支援觸發 64 位元 2016 Click-隨選即用版本的 Office 從 Microsoft 365 商務系統管理主控台。</span><span class="sxs-lookup"><span data-stu-id="35c25-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="35c25-p103">**沒有**任何 2016 Windows Installer (MSI) 獨立應用程式 （例如，Visio 或 Project）。Microsoft 365 商務 Click-隨選即用版本的 Office 2016 升級 Office 並不適用於與 Office 2016 MSI 獨立應用程式。</span><span class="sxs-lookup"><span data-stu-id="35c25-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="35c25-120">下表是使用者/系統管理員可能需要採取的動作 (視起始狀態而定) 的詳細資料，以便從 Microsoft 365 商務版系統管理主控台成功部署 32 位元的隨選即用版本 Office。</span><span class="sxs-lookup"><span data-stu-id="35c25-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="35c25-121">**啟動 Office 安裝狀態**</span><span class="sxs-lookup"><span data-stu-id="35c25-121">**Starting Office install status**</span></span>|<span data-ttu-id="35c25-122">**在安裝 Microsoft 365 商務版 Office 之前需採取的動作**</span><span class="sxs-lookup"><span data-stu-id="35c25-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="35c25-123">**結束狀態**</span><span class="sxs-lookup"><span data-stu-id="35c25-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="35c25-124">未安裝任何 Office 套件</span><span class="sxs-lookup"><span data-stu-id="35c25-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="35c25-125">無</span><span class="sxs-lookup"><span data-stu-id="35c25-125">None</span></span>  <br/> |<span data-ttu-id="35c25-126">使用隨選即用安裝 32 位元 Office 2016</span><span class="sxs-lookup"><span data-stu-id="35c25-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="35c25-127">現有的隨選即用 32 位元版本的 Office (2016 或更舊版本)，且沒有獨立版本 App</span><span class="sxs-lookup"><span data-stu-id="35c25-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="35c25-128">無</span><span class="sxs-lookup"><span data-stu-id="35c25-128">None</span></span>  <br/> |<span data-ttu-id="35c25-129">升級為最新 32 位元 Click-隨選即用版本的 Office 2016 視**\***</span><span class="sxs-lookup"><span data-stu-id="35c25-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="35c25-130">現有的隨選即用 32 位元版本的 Office，以及隨選即用的 32 或 64 位元獨立版本 Office App (例如 Visio、Project)</span><span class="sxs-lookup"><span data-stu-id="35c25-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="35c25-131">無</span><span class="sxs-lookup"><span data-stu-id="35c25-131">None</span></span>  <br/> |<span data-ttu-id="35c25-p104">獨立版本 App 不會受到影響。套件已升級到隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="35c25-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="35c25-134">現有的隨選即用 32 位元版本的 Office，以及任何 32 位元或 64 位元 (2016 除外) MSI 獨立版本 Office App</span><span class="sxs-lookup"><span data-stu-id="35c25-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="35c25-135">無</span><span class="sxs-lookup"><span data-stu-id="35c25-135">None</span></span>  <br/> |<span data-ttu-id="35c25-p105">獨立版本 App 不會受到影響。套件已升級到隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="35c25-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="35c25-138">任何現有的隨選即用 64 位元版本的 Office</span><span class="sxs-lookup"><span data-stu-id="35c25-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="35c25-139">解除安裝 64 位元 Office App (如果可以用 32 位元 Office App 取代的話)</span><span class="sxs-lookup"><span data-stu-id="35c25-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="35c25-140">如果 Office 64 位元 App 遭到移除，則會安裝隨選即用 32 位元版本的 Office 2016</span><span class="sxs-lookup"><span data-stu-id="35c25-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="35c25-141">包含或不包含獨立版本 App 之現有的 MSI Office 2016 安裝</span><span class="sxs-lookup"><span data-stu-id="35c25-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="35c25-142">解除安裝 MSI Office 2016。</span><span class="sxs-lookup"><span data-stu-id="35c25-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="35c25-p106">已安裝隨選即用 32 位元版本的 Office 2016。不會變更獨立版本 App</span><span class="sxs-lookup"><span data-stu-id="35c25-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="35c25-145">現有的 MSI Office 2013 (或更舊版本) 安裝和/或獨立版本 Office App</span><span class="sxs-lookup"><span data-stu-id="35c25-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="35c25-146">無</span><span class="sxs-lookup"><span data-stu-id="35c25-146">None</span></span>  <br/> |<span data-ttu-id="35c25-147">隨選即用 32 位元版本的 Office 2016 與既有的 MSI Office 安裝 (和獨立版本 App) 並存</span><span class="sxs-lookup"><span data-stu-id="35c25-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="35c25-p107">**(\*) 附註：** 無法升級為 Office 2016 因已知錯誤而按一下來執行 32 位元版本。修正正在進行中。</span><span class="sxs-lookup"><span data-stu-id="35c25-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


