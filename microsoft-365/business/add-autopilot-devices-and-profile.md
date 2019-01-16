---
title: 使用逐步指南新增 Autopilot 裝置和設定檔
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
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
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows 自動駕駛儀上設定為貴公司的新 Windows 10 裝置。
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866117"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>使用逐步指南新增 Autopilot 裝置和設定檔

您可以使用 Windows AutoPilot 為貴公司設定新的 Windows 10 裝置，在員工獲得您提供的裝置時，就能立即使用並發揮生產力。
  
## <a name="device-requirements"></a>裝置需求

裝置必須符合這些需求：
  
- Windows 10 版本 1703 或更新版本。
    
- 新裝置尚未執行過 Windows 全新體驗設定。
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>使用設定指南建立裝置和設定檔

如果您尚未建立裝置群組或設定檔，最佳的開始使用方式是使用逐步指南，但您也可以[新增裝置](create-and-edit-autopilot-devices.md)及[指派設定檔](create-and-edit-autopilot-profiles.md)給裝置，而不使用指南。 
  
1. 在 Microsoft 365 商務系統管理中心中，找到**裝置動作**卡片，然後選擇 [**使用自動駕駛儀上部署 Windows**。
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. 在 [**準備 Windows** ] 頁面上按一下或點選**啟動指南 》**。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. 在 [**上傳.csv 檔案的裝置清單**] 頁面上，瀏覽至您已準備好位置。CSV 檔案，然後**開啟** \> **下一步**。檔案應該有三個標頭：
    
  - 欄 A：裝置序號
    
  - 欄 B：Windows 產品識別碼
    
  - 欄 C：硬體雜湊
    
    您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。 
    
    如需詳細資訊，請參閱[CSV 檔案的裝置清單](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。您也可以下載 [**上傳.csv 檔案的裝置清單**] 頁面上的範例檔案。 
    
4. 在 [**指定設定檔**] 頁面上可以選擇現有的設定檔，或建立一個新。如果您沒有一個尚未，系統會提示您建立一個新。 
    
    設定檔是可套用到單一裝置或一組裝置的設定集合。
    
    預設功能是必要的，而且會自動設定。預設功能包括：
    
  - 略過 Cortana、OneDrive 及 OEM 註冊。
    
  - 使用公司品牌建立登入體驗。
    
  - 裝置即將連線到 Azure Active Directory 帳戶，而且會自動註冊為受 Microsoft 365 商務版管理。
    
    如需詳細資訊，請參閱
    
    [關於 AutoPilot 設定檔的設定](autopilot-profile-settings.md) 。 
    
5. 其他設定會**略過隱私權設定**並**不允許使用者可以成為本機管理員**。這些皆被設為**關閉**預設。 
    
    選擇 [**下一步**]。
    
6. **完成**] 頁面上會指出建立 （或選擇） 的設定檔將會套用到您所上傳的裝置清單建立裝置群組。這些設定會對時裝置使用者登入下一步]。選擇 [**關閉**]。
    