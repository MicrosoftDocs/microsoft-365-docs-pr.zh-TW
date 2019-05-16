---
title: 建立及編輯 AutoPilot 設定檔
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: '了解如何建立、 編輯、 刪除或移除 AutoPilot 設定檔。 '
ms.openlocfilehash: 7987cafb3ea234d81be72c79aee8e584a3770875
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073483"
---
# <a name="create-and-edit-autopilot-profiles"></a>建立及編輯 AutoPilot 設定檔

## <a name="create-a-profile"></a>建立設定檔

設定檔適用於單一裝置或一組裝置。
  
1. 在 Microsoft 365 商務版系統管理中心中，選擇 [**裝置**] \> **AutoPilot**。
  
2. 在**自動駕駛**頁面上，選擇 [**設定檔**] 索引標籤\>**建立設定檔**。
    
3. 在 [**建立設定檔**] 頁面上，輸入可協助您識別，例如行銷，開啟您想要 （如需詳細資訊，請參閱[關於 AutoPilot 設定檔設定](autopilot-profile-settings.md)，） 的設定，然後選擇 [**儲存**設定檔的名稱。
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>將設定檔套用到裝置

建立設定檔之後，您可以將它套用到單一裝置或一組裝置。您可以在[逐步指南](add-autopilot-devices-and-profile.md)中挑選現有設定檔、可以將設定檔套用到新裝置，或者也可以取代單一裝置或一組裝置的現有設定檔。 
  
1. 在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤。 
    
2. 按一下核取方塊，裝置名稱旁邊，然後在 [**裝置**] 面板中，從**指派的設定檔**下拉式清單中選擇設定檔\>**儲存**。
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>編輯、刪除或移除設定檔

一旦為裝置指派設定檔後，即使您已將裝置提供給使用者，您仍可更新設定檔。當裝置連線到網際網路時，它會在設定程序期間下載您的最新版設定檔。如果使用者將其裝置還原為其原廠預設設定，裝置會將最新更新再次下載到您的設定檔。 
  
### <a name="edit-a-profile"></a>編輯設定檔

1. 在 [**準備 Windows** ] 頁面上，選擇 [**設定檔**] 索引標籤。 
    
2. 按一下裝置名稱旁邊的核取方塊，並在 [**設定檔**] 面板更新任何可用設定\>**儲存**。
    
    如果您在使用者將裝置連線到網際網路之前這麼做，設定檔則會套用到設定程序。
    
### <a name="delete-a-profile"></a>刪除設定檔

1. 在 [**準備 Windows** ] 頁面上，選擇 [**設定檔**] 索引標籤。 
    
2. 按一下裝置名稱旁邊的核取方塊，然後在 [**設定檔**] 面板中按一下 [**刪除設定檔** \> **儲存**。
    
    當您刪除設定檔時，會移除單一裝置或一組裝置中的獲派設定檔。
    
### <a name="remove-a-profile"></a>移除設定檔

1. 在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤。 
    
2. 按一下核取方塊，裝置名稱旁邊，然後在 [**裝置**] 面板中，從**指派的設定檔**下拉式清單選擇 [**無** \> **儲存**。
    
