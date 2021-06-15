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
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>為商務 Microsoft 365 準備 Office 用戶端部署

本文適用于 Microsoft 365 商務進階版。

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>準備將 Office App 自動安裝到用戶端電腦

您可以使用 Microsoft 365 商務進階版在 Windows 10 電腦上自動安裝32位 Office 應用程式，並將更新維持在最新狀態。
  
如果使用者的電腦位於 Windows 10 商務版，則自動安裝效果最好，且：
  
- 沒有現有的 Office 傳統型應用程式 (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive)。
    
    或
    
- 已安裝現有版本的隨選即用 Office。
    
若要判斷您是否有 Office 的 Click-to-Run 版本，請在任何 Office 應用程式移 **至檔案** \> **帳戶** ( Office Outlook 中的 **帳戶**。 如果您看到 **Office 的更新** 如下圖所示，則是使用 Click-to-Run 進行安裝。 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **利用這項功能神秘好處**
  
電腦符合下列情況的使用者：
  
- **具有** Windows 10 商務版使用者授權、商務用 Microsoft 365 商務版授權、Windows 10 建立者更新，以及加入 Azure Active Directory。 
    
- Office 應用程式 **沒有64位** (範例： Word、Excel PowerPoint) 。 如果需要64位 Office 應用程式，則這項功能不是很好的，因為不支援從 business administration console 的 Microsoft 365 觸發64位 2016 Click-to-Run 版本的 Office。 
    
- **沒有任何 2016** Windows 安裝程式 (MSI) 獨立應用程式 (例如 Visio 或 Project) 。 Microsoft 365 以進行商務升級 Office Click-to-Run 版本的 Office 2016，而且無法使用 Office 2016 MSI 獨立應用程式。 
    
下表顯示使用者/系統管理員可能需要採取的動作，視其開始狀態而定，若要從 business admin console Microsoft 365 取得32成功的 Office 部署 Click-to-Run 版本。<br/>


|啟動 Office 安裝狀態|在 Microsoft 365 商務 Office 安裝之前採取的動作|結束狀態|
|:-----|:-----|:-----|
|未安裝任何 Office 套件  <br/> |無  <br/> |使用 Click-to-Run 安裝 Office 2016 32 位  <br/> |
|現有的隨選即用 32 位元版本的 Office (2016 或更舊版本)，且沒有獨立版本 App  <br/> |無  <br/> |視需要升級為 Office 2016 的最新32位 Click-to-Run 版本 **\*** <br/> |
|現有 Click-to-Run 32 位版本的 Office 和 Click-to-Run 32 位或64位獨立 Office 應用程式 (例如 Visio、Project)   <br/> |無  <br/> |獨立應用程式不會受到影響。 套件已升級到隨選即用 32 位元版本的 Office 2016  <br/> |
|現有的隨選即用 32 位元版本的 Office，以及任何 32 位元或 64 位元 (2016 除外) MSI 獨立版本 Office App  <br/> |無  <br/> |獨立應用程式不會受到影響。 套件已升級到隨選即用 32 位元版本的 Office 2016  <br/> |
|任何現有的隨選即用 64 位元版本的 Office  <br/> |卸載64位 Office 應用程式（如果有的話）以32位 Office 應用程式來取代它們  <br/> |如果 Office 64 位元 App 遭到移除，則會安裝隨選即用 32 位元版本的 Office 2016  <br/> |
|包含或不包含獨立版本 App 之現有的 MSI Office 2016 安裝  <br/> |解除安裝 MSI Office 2016。  <br/> |已安裝隨選即用 32 位元版本的 Office 2016。不會變更獨立版本 App  <br/> |
|現有的 MSI Office 2013 (或更舊版本) 安裝和/或獨立版本 Office App  <br/> |無  <br/> |隨選即用 32 位元版本的 Office 2016 與既有的 MSI Office 安裝 (和獨立版本 App) 並存  <br/> |
||||
   
 **(\*) 附注：** 由於已知的錯誤，不會升級為 Office 2016 的 Click-to-Run 32 位版本。 修正程式正在進行中。 
  
