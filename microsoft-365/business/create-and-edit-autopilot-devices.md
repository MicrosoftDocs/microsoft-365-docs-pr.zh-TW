---
title: 建立及編輯 AutoPilot 裝置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 瞭解如何使用 Microsoft 365 商務版 Premium 中的 AutoPilot 上傳裝置。 您可以將設定檔指派給裝置或裝置群組。
ms.openlocfilehash: 910abb98b94b749177b04cd12c766f82d348e379
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913391"
---
# <a name="create-and-edit-autopilot-devices"></a>建立及編輯 AutoPilot 裝置

## <a name="upload-a-list-of-devices"></a>上傳裝置清單

您可以使用逐步 [指南](add-autopilot-devices-and-profile.md) 來上傳裝置，但是您也可以在 [ **裝置** ] 索引標籤中上傳裝置。 
  
裝置必須符合下列需求：
  
- Windows 10，版本1703或更新版本
    
- 尚未透過 Windows 現成體驗的新裝置

1. 在 Microsoft 365 系統管理中心，選擇 [ **裝置**] \> **AutoPilot**。
  
2. 在 [ **AutoPilot** ] 頁面上，選擇 [ **裝置** ] 索引標籤 [ \> **新增裝置**]。
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 在 [**新增裝置**] 面板上，流覽至您準備儲存關閉的 [裝置清單 CSV](../admin/misc/device-list.md)檔案 \>  \> ****。
    
    您可以從硬體廠商取得此資訊，也可以使用 [Get-WindowsAutoPilotInfo PowerShell 腳本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 來產生 CSV 檔案。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>針對裝置或裝置群組指派設定檔

1. 在 [ **準備 Windows** ] 頁面上，選擇 [ **裝置** ] 索引標籤，然後選取一或多個裝置旁的核取方塊。 
    
2. 在 [ **裝置** ] 面板上，從 [ **已指派的設定檔** ] 下拉式清單中選取設定檔。 
    
    如果您沒有任何設定檔，請參閱[建立及編輯 AutoPilot 設定檔](create-and-edit-autopilot-profiles.md)以取得相關指示。 
