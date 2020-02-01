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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 了解如何上傳 Microsoft 365 商務版中使用 AutoPilot 裝置。 您可以將設定檔指派到單一裝置或一組裝置。
ms.openlocfilehash: 5a99f691b0325f511f34e3a6c3a20f08ee8d909f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594004"
---
# <a name="create-and-edit-autopilot-devices"></a>建立及編輯 AutoPilot 裝置

## <a name="upload-a-list-of-devices"></a>上傳裝置清單

您可以使用[逐步指南](add-autopilot-devices-and-profile.md)來上傳裝置，但您也可以上傳**裝置**] 索引標籤中的裝置。 
  
裝置必須符合這些需求：
  
- Windows 10 版本 1703 或更新版本
    
- 新裝置尚未透過 Windows 現成可用的經驗

1. 在 Microsoft 365 商務版系統管理中心中，選擇 [**裝置**] \> **AutoPilot**。
  
2. 在**自動駕駛**頁面上，選擇 [**裝置**] 索引標籤\>**新增裝置**。
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 在 [**新增裝置**] 面板中，瀏覽至您備妥的[裝置清單 CSV 檔案](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) \> **儲存** \> **關閉**。
    
    您可以從您的硬體廠商取得這項資訊，或您可以使用[Get-windowsautopilotinfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)來產生 CSV 檔案。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>針對裝置或裝置群組指派設定檔

1. 在 [**準備 Windows** ] 頁面上選擇 [**裝置**] 索引標籤，並選取一個或多個裝置旁的核取方塊。 
    
2. 在 [**裝置**] 面板中，選取 [設定檔從**指派的設定檔**下拉式清單。 
    
    如果您沒有任何設定檔，請參閱[建立及編輯 AutoPilot 設定檔](create-and-edit-autopilot-profiles.md)以取得相關指示。 
    
