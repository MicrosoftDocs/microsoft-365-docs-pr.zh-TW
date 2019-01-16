---
title: 建立及編輯 AutoPilot 裝置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 了解如何上傳 Microsoft 365 Business 中使用自動駕駛儀上的裝置。您可以將設定檔指派給裝置或裝置群組。
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866368"
---
# <a name="create-and-edit-autopilot-devices"></a>建立及編輯 AutoPilot 裝置

## <a name="upload-a-list-of-devices"></a>上傳裝置清單

您可以使用[逐步指南](add-autopilot-devices-and-profile.md)上傳裝置，但您也可以上傳**裝置**] 索引標籤中。 
  
裝置必須符合這些需求：
  
- Windows 10 版本 1703 或更新版本。
    
- 新裝置尚未執行過 Windows 全新體驗設定。
    
1. 在 Microsoft 365 商務系統管理中心中，選擇 [**使用自動駕駛儀上部署 Windows** **裝置動作**卡片上。 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. 在 [**準備 Windows** ] 頁面上選擇 [**裝置**] 索引標籤\>**新增裝置**。
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 在 [**新增裝置**] 面板中，瀏覽至您已準備[CSV 檔案的裝置清單](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) \> **儲存** \> **關閉**。
    
    您可以從硬體廠商取得這項資訊，或是使用可產生 csv 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>針對裝置或裝置群組指派設定檔

1. 在 [**準備 Windows** ] 頁面上選擇 [**裝置**] 索引標籤及一或多個裝置] 旁的核取方塊。 
    
2. 在 [**裝置**] 面板中，選取一個設定檔從**已指派] 設定檔**] 下拉式清單。 
    
    如果您沒有任何設定檔，請參閱[建立及編輯 AutoPilot 設定檔](create-and-edit-autopilot-profiles.md)以取得相關指示。 
    
