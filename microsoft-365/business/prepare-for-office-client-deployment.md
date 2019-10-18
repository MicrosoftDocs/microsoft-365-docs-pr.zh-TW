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
description: 了解如何自動安裝 32 位元 Office app 到 Windows 10 電腦，並讓這些更新。
ms.openlocfilehash: 5b28c1e62d813c52b41ce8e7619c865cdf7690e2
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575811"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>透過 Microsoft 365 商務版準備 Office 用戶端部署

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>準備將 Office App 自動安裝到用戶端電腦

您可以使用 Microsoft 365 商務版將 32 位元的 Office App 自動安裝到 Windows 10 電腦，並讓這些 App 保持最新狀態。
  
此功能適用於搭載 Windows 10 商務版且符合以下情況的電腦：
  
- 沒有現有的 Office 傳統型應用程式 (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive)。
    
    或
    
- 已安裝現有版本的隨選即用 Office。
    
若要判斷是否有按一下-隨選即用版本的 Office，在任何 Office 應用程式移至 [**檔案** \> **帳戶**（在 Outlook 中的**Office 帳戶**）。 如果您看到如下圖所示的 Office 更新，表示安裝程序是使用隨選即用完成。 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **誰會藉由這項功能獲益**
  
電腦符合下列情況的使用者：
  
- **具有**Windows 10 商務版使用者授權，作用中的 Microsoft 365 商務版授權，Windows 10 Creators Update，且已加入 Azure Active Directory。 
    
- **沒有**64 位元 Office app (範例： Word、 Excel、 Powerpoint)。 如果需要 64 位元的 Office App，則不適用這項功能，因為無法從 Microsoft 365 商務版系統管理主控台觸發 64 位元的 2016 隨選即用版本的 Office。 
    
- **沒有**任何 2016 Windows Installer (MSI) 獨立應用程式 （例如 Visio 或 Project）。 Microsoft 365 商務版會將 Office 升級為隨選即用版本的 Office 2016，但這不支援 Office 2016 MSI 獨立版本 App。 
    
下表是使用者/系統管理員可能需要採取的動作 (視起始狀態而定) 的詳細資料，以便從 Microsoft 365 商務版系統管理主控台成功部署 32 位元的隨選即用版本 Office。
  
|**啟動 Office 安裝狀態**|**在安裝 Microsoft 365 商務版 Office 之前需採取的動作**|**結束狀態**|
|:-----|:-----|:-----|
|未安裝任何 Office 套件  <br/> |無  <br/> |使用隨選即用安裝 32 位元 Office 2016  <br/> |
|現有的隨選即用 32 位元版本的 Office (2016 或更舊版本)，且沒有獨立版本 App  <br/> |無  <br/> |視需要升級至最新的 32 位元按一下-隨選即用版本的 Office 2016，**\*** <br/> |
|現有的隨選即用 32 位元版本的 Office，以及隨選即用的 32 或 64 位元獨立版本 Office App (例如 Visio、Project)  <br/> |無  <br/> |獨立版本 App 不會受到影響。套件已升級到隨選即用 32 位元版本的 Office 2016  <br/> |
|現有的隨選即用 32 位元版本的 Office，以及任何 32 位元或 64 位元 (2016 除外) MSI 獨立版本 Office App  <br/> |無  <br/> |獨立版本 App 不會受到影響。套件已升級到隨選即用 32 位元版本的 Office 2016  <br/> ||||
|任何現有的隨選即用 64 位元版本的 Office  <br/> |解除安裝 64 位元 Office App (如果可以用 32 位元 Office App 取代的話)  <br/> |如果 Office 64 位元 App 遭到移除，則會安裝隨選即用 32 位元版本的 Office 2016  <br/> |
|包含或不包含獨立版本 App 之現有的 MSI Office 2016 安裝  <br/> |解除安裝 MSI Office 2016。  <br/> |已安裝隨選即用 32 位元版本的 Office 2016。不會變更獨立版本 App  <br/> |
|現有的 MSI Office 2013 (或更舊版本) 安裝和/或獨立版本 Office App  <br/> |無  <br/> |隨選即用 32 位元版本的 Office 2016 與既有的 MSI Office 安裝 (和獨立版本 App) 並存  <br/> |
||||
   
 **(\*) 附註：** 不會升級到按一下 [若要執行 32 位元版本的 Office 2016 由於已知的錯誤。 我們正在修正此問題。 
  


