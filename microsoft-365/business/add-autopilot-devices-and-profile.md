---
title: 使用逐步指南新增 Autopilot 裝置和設定檔
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
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
description: 了解如何使用 Windows AutoPilot 為貴公司的新 Windows 10 裝置上設定。
ms.openlocfilehash: 8c4a14b4b9dcbf7a30c1e6e0bdd53418a1ab8a03
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660649"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>使用逐步指南新增 Autopilot 裝置和設定檔

您可以使用 Windows AutoPilot 來讓裝置備妥用於工作生產，為您提供給您的員工貴公司設定**新**的 Windows 10 裝置上。
  
## <a name="device-requirements"></a>裝置需求

裝置必須符合這些需求：
  
- Windows 10 版本 1703 或更新版本。
    
- 新裝置尚未執行過 Windows 全新體驗設定。
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>使用設定指南建立裝置和設定檔

![指向橫幅https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

如果您尚未建立裝置群組或設定檔，最佳的開始使用方式是使用逐步指南，但您也可以[新增裝置](create-and-edit-autopilot-devices.md)及[指派設定檔](create-and-edit-autopilot-profiles.md)給裝置，而不使用指南。 
  
1. 移至系統管理中心， <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。

2. 在左側導覽中選擇 [**裝置** \> **AutoPilot**。

    ![在系統管理中心選擇 [裝置，然後自動駕駛。](media/AutoPilot.png)
  
2. 在**自動駕駛**頁面上，按一下或點選 [**開始指南**。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. 在 [**上傳裝置清單的.csv 檔案**] 頁面上，瀏覽到您已準備好位置。CSV 檔案，然後**開啟** \> **下一步**。 檔案應該會有三個標題：
    
  - 欄 A：裝置序號
    
  - 欄 B：Windows 產品識別碼
    
  - 欄 C：硬體雜湊
    
    您可以從硬體廠商取得這項資訊，或是使用可產生 CSV 檔案的 [Get-WindowsAutoPilotInfo PowerShell 指令碼](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) (英文)。 
    
    如需詳細資訊，請參閱[裝置清單 CSV 檔案](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。 您也可以下載範例檔案**上傳裝置清單的.csv 檔案**] 頁面上。 
    
4. 在**指派設定檔**] 頁面中，您可以挑選現有設定檔，或建立一個新。 如果您還沒有設定檔，您將看到建立設定檔的提示。 
    
    設定檔是可套用到單一裝置或一組裝置的設定集合。
    
    預設功能是必要的，而且會自動設定。預設功能包括：
    
  - 略過 Cortana、OneDrive 及 OEM 註冊。
    
  - 使用公司品牌建立登入體驗。
    
  - 裝置即將連線到 Azure Active Directory 帳戶，而且會自動註冊為受 Microsoft 365 商務版管理。
    
    如需詳細資訊，請參閱
    
    [關於 AutoPilot 設定檔的設定](autopilot-profile-settings.md) 。 
    
5. 其他設定，而**略過的隱私權設定****不會讓使用者成為本機系統管理員**。這些都設定為**Off**預設。 
    
    選擇 [下一步]****。
    
6. **大功告成**] 頁面會指出您建立 （或選擇） 的設定檔將會套用至您建立所上傳裝置清單的裝置群組。 這些設定會在裝置使用者下次登入時生效。 選擇 [**關閉**]。
    