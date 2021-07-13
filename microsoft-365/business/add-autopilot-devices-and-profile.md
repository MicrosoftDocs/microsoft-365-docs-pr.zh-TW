---
title: 使用逐步指南新增 Autopilot 裝置和設定檔
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 瞭解如何使用 Windows AutoPilot 為您的公司設定新的 Windows 10 裝置，使其可供員工使用。
ms.openlocfilehash: f160ddcd1e41bd44c908ecc8bbd30a9819f76902
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393432"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>使用逐步指南新增 Autopilot 裝置和設定檔

您可以使用 Windows AutoPilot 為您的公司設定 **新** 的 Windows 10 裝置，以便在您將其授與員工時使用。
  
## <a name="device-requirements"></a>裝置需求

裝置必須符合下列需求：
  
- Windows 10，版本1703或更新版本
    
- 尚未透過 Windows 全新體驗的新裝置
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>使用設定指南建立裝置和設定檔

若尚未建立裝置群組或設定檔，最好的入門方式是使用逐步指南。 您也可以 [新增裝置](create-and-edit-autopilot-devices.md) ，並 [將設定檔指派](create-and-edit-autopilot-profiles.md) 給它們，而不需使用輔助線。 
  
1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

2. 在左功能窗格中，選擇 [ **裝置**] \> **AutoPilot**。

    ![在系統管理中心中，選擇 [裝置]，然後 AutoPilot]。](../media/AutoPilot.png)
  
2. 在 [ **AutoPilot** ] 頁面上，按一下或點擊 [ **開始指南**]。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. 在 [ **Upload .csv 具有裝置清單的** 檔案] 頁面上，流覽至您已準備好 .CSV 檔案的位置，然後 **開啟** \> **[下一步]**。 檔案必須有三個標頭：
    
    - 欄 A：裝置序號
    
    - 欄 B：Windows 產品識別碼
    
    - 欄 C：硬體雜湊
    
    您可以從硬體廠商取得此資訊，也可以使用 [Get-WindowsAutoPilotInfo PowerShell 腳本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 來產生 CSV 檔案。 
    
    如需詳細資訊，請參閱[裝置清單 CSV 檔案](../admin/misc/device-list.md)。 您也可以 **使用 [裝置清單**] 頁面，在 [Upload .csv 檔案] 頁面上下載範例檔案。 
    
> [!NOTE]
> 此腳本會使用 WMI 來取得客戶使用 Windows Autopilot 註冊裝置所需的屬性。 請注意，產生的 CSV 檔案不會收集 Windows 產品識別碼 (PKID) 值，因為不需要在輸出 CSV 中註冊裝置及 PKID 為 Null，就完全正確。 只會填入序號碼和硬體雜湊。
    
4. 在 [ **指派設定檔** ] 頁面上，您可以挑選現有的設定檔或建立新的設定檔。 如果您還沒有，系統會提示您建立一個。 
    
    設定檔是可套用到單一裝置或一組裝置的設定集合。
    
    預設功能是必要的，且會自動設定。 預設功能包括：
    
    - 略過 Cortana、OneDrive 和 OEM 註冊。
    
    - 使用公司品牌建立登入體驗。
    
    - 連線您的裝置以 Azure Active Directory 帳戶，並自動將其註冊為由 Microsoft 365 商務進階版進行管理。
    
    如需詳細資訊，請參閱 [關於 AutoPilot 設定檔設定](autopilot-profile-settings.md)。 
    
5. 其他設定則 **略過隱私權設定** ，而 **不允許使用者成為本機系統管理員**。這些皆預設會設為 **Off** 。 
    
    選擇 ****[下一步]。
    
6. **您已完成** 表示您已建立的設定檔 (或選擇) 會套用到您透過上載裝置清單所建立的裝置群組。 當裝置使用者下一次登入時，設定就會生效。 選擇 [ **關閉**]。

## <a name="related-content"></a>相關內容

[關於 AutoPilot 設定檔設定](autopilot-profile-settings.md) (文章) \
[保護裝置及應用程式資料的選項](../admin/devices/choose-device-security.md) (文章) 
