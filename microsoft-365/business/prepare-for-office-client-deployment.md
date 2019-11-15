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
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>透過 Microsoft 365 商務版準備 Office 用戶端部署

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>準備將 Office App 自動安裝到用戶端電腦

您可以使用 Microsoft 365 商務版，自動在 Windows 10 電腦上安裝 32 位元 Office app，並維持更新。
  
自動安裝適合如果使用者的電腦在 Windows 10 商務版和：
  
- 沒有現有的 Office 傳統型應用程式 (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive)。
    
    或
    
- 已安裝現有版本的隨選即用 Office。
    
若要判斷是否有按一下-隨選即用版本的 Office，在任何 Office 應用程式移至 [**檔案** \> **帳戶**（在 Outlook 中的**Office 帳戶**）。 如果您看到**Office 更新**，如下圖所示，安裝已完成使用 Click-隨選即用。 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **誰福利由這項功能**
  
電腦符合下列情況的使用者：
  
- **具有**Windows 10 商務版使用者授權，作用中的 Microsoft 365 商務版授權，Windows 10 Creators Update，且已加入 Azure Active Directory。 
    
- **沒有**64 位元 Office app (範例： Word、 Excel、 PowerPoint)。 如果 64 位元 Office app 是必要的則這項功能不適合，因為不支援觸發 64 位元 2016年按一下-隨選即用版本的 Office 從 Microsoft 365 商務版系統管理主控台。 
    
- **沒有**任何 2016 Windows Installer (MSI) 獨立應用程式 （例如 Visio 或 Project）。 Microsoft 365 商務版 Office 升級為按一下-隨選即用版本的 Office 2016 及，不適用於 Office 2016 MSI 獨立版本 app。 
    
下表顯示哪些巨集指令的使用者/系統管理員可能需要執行，根據其開頭的狀態，成功的 32 位元按一下-隨選即用版本的 Office 部署 Microsoft 365 商務版系統管理主控台。
  
|**啟動 Office 安裝狀態**|**在安裝 Microsoft 365 商務版 Office 之前需採取的動作**|**結束狀態**|
|:-----|:-----|:-----|
|未安裝任何 Office 套件  <br/> |無  <br/> |藉由按一下 [-隨選即用安裝 office 2016 32年位元  <br/> |
|現有的隨選即用 32 位元版本的 Office (2016 或更舊版本)，且沒有獨立版本 App  <br/> |無  <br/> |視需要升級至最新的 32 位元按一下-隨選即用版本的 Office 2016，**\*** <br/> |
|現有的按一下 [若要執行 32 位元版本的 Office 並按一下 [若要執行 32 位元或 64 位元獨立 Office 應用程式 （例如，Visio、 Project）  <br/> |無  <br/> |獨立版本 app 不受影響。 套件已升級到隨選即用 32 位元版本的 Office 2016  <br/> |
|現有的隨選即用 32 位元版本的 Office，以及任何 32 位元或 64 位元 (2016 除外) MSI 獨立版本 Office App  <br/> |無  <br/> |獨立版本 app 不受影響。 套件已升級到隨選即用 32 位元版本的 Office 2016  <br/> ||||
|任何現有的隨選即用 64 位元版本的 Office  <br/> |如果是 [確定] 以將它取代為 32 位元 Office 應用程式解除安裝 64 位元 Office 應用程式]，  <br/> |如果 Office 64 位元 App 遭到移除，則會安裝隨選即用 32 位元版本的 Office 2016  <br/> |
|包含或不包含獨立版本 App 之現有的 MSI Office 2016 安裝  <br/> |解除安裝 MSI Office 2016。  <br/> |已安裝隨選即用 32 位元版本的 Office 2016。不會變更獨立版本 App  <br/> |
|現有的 MSI Office 2013 (或更舊版本) 安裝和/或獨立版本 Office App  <br/> |無  <br/> |隨選即用 32 位元版本的 Office 2016 與既有的 MSI Office 安裝 (和獨立版本 App) 並存  <br/> |
||||
   
 **(\*) 附註：** 不會升級到按一下 [若要執行 32 位元版本的 Office 2016 由於已知的錯誤。 修正正在進行中。 
  