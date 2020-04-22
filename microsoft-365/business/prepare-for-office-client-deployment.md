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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 瞭解如何在 Windows 10 電腦上自動安裝32位 Office 應用程式，並將其保持更新。
ms.openlocfilehash: b5f01bc9bb10765929f3c6bdd5908e8b48a51a11
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633092"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Microsoft 365 for business 準備 Office 用戶端部署

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>準備將 Office App 自動安裝到用戶端電腦

您可以使用 Microsoft 365 for business，在 Windows 10 電腦上自動安裝32位 Office 應用程式，並將更新維持在最新狀態。
  
如果使用者的電腦在 Windows 10 商務版上，則自動安裝效果最好，而且：
  
- 沒有現有的 Office 傳統型應用程式 (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive)。
    
    或
    
- 已安裝現有版本的隨選即用 Office。
    
若要判斷您是否有 office 的 Click-to-Run 版本，請在任何 Office 應用程式**中，移至** \> [檔案**帳戶**（Outlook 中的**Office 帳戶**）]。 如果您看到如下圖所示的**Office 更新**，則是使用 Click-to-Run 執行安裝。 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **享受此功能的好處**
  
電腦符合下列情況的使用者：
  
- **具有**Windows 10 商務版使用者授權、使用中 Microsoft 365 for Business 授權、Windows 10 創意者更新，以及加入 Azure active Directory。 
    
- **沒有64位**的 Office app （例如： Word、Excel、PowerPoint）。 如果需要64位的 Office app，這項功能不是很好的，因為不支援從 Microsoft 365 for business 管理主控台觸發64位的 2016 Click-to-Run 版本的 Office。 
    
- **沒有任何 2016** Windows INSTALLER （MSI）獨立應用程式（例如 Visio 或 Project）。 Microsoft 365 for business 將 Office 升級至 Office 2016 的 Click-to-Run 版本，但無法搭配 Office 2016 MSI 獨立應用程式使用。 
    
下表顯示使用者/系統管理員可能需要採取的動作，視其開始狀態而定，若要從 Microsoft 365 for business 系統管理主控台取得成功的 Office 部署32位 Click-to-Run 版本。
  
|**啟動 Office 安裝狀態**|**Microsoft 365 for business Office 安裝前所要採取的動作**|**結束狀態**|
|:-----|:-----|:-----|
|未安裝任何 Office 套件  <br/> |無  <br/> |使用 Click-to-Run 安裝 Office 2016 32 位  <br/> |
|現有的隨選即用 32 位元版本的 Office (2016 或更舊版本)，且沒有獨立版本 App  <br/> |無  <br/> |視需要升級至最新的32位 Click-to-Run 版本的 Office 2016**\*** <br/> |
|現有 Click-to-Run 32 位版本的 Office，以及 Click-to-Run 32 位或64位獨立 Office 應用程式（例如 Visio、Project）  <br/> |無  <br/> |獨立應用程式不會受到影響。 套件已升級到隨選即用 32 位元版本的 Office 2016  <br/> |
|現有的隨選即用 32 位元版本的 Office，以及任何 32 位元或 64 位元 (2016 除外) MSI 獨立版本 Office App  <br/> |無  <br/> |獨立應用程式不會受到影響。 套件已升級到隨選即用 32 位元版本的 Office 2016  <br/> ||||
|任何現有的隨選即用 64 位元版本的 Office  <br/> |卸載64位 Office 應用程式（如果有的話）以32位 Office app 取代它們  <br/> |如果 Office 64 位元 App 遭到移除，則會安裝隨選即用 32 位元版本的 Office 2016  <br/> |
|包含或不包含獨立版本 App 之現有的 MSI Office 2016 安裝  <br/> |解除安裝 MSI Office 2016。  <br/> |已安裝隨選即用 32 位元版本的 Office 2016。不會變更獨立版本 App  <br/> |
|現有的 MSI Office 2013 (或更舊版本) 安裝和/或獨立版本 Office App  <br/> |無  <br/> |隨選即用 32 位元版本的 Office 2016 與既有的 MSI Office 安裝 (和獨立版本 App) 並存  <br/> |
||||
   
 **（\*）注意：** 不會升級為 Click-to-Run 32 位版本的 Office 2016，因為有已知的錯誤。 修正程式正在進行中。 
  
