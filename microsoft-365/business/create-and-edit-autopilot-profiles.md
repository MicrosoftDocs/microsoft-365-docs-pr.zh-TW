---
title: 建立及編輯 AutoPilot 設定檔
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 瞭解如何建立 AutoPilot 設定檔，並將其套用至裝置，以及編輯或刪除設定檔，或從裝置移除設定檔。
ms.openlocfilehash: e58418813ed0b4d23a5fa7e1d23aae33d8850e7f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400967"
---
# <a name="create-and-edit-autopilot-profiles"></a>建立及編輯 AutoPilot 設定檔

## <a name="create-a-profile"></a>建立設定檔

設定檔適用於單一裝置或一組裝置。
  
1. 在 Microsoft 365 系統管理中心，選擇 [**裝置**] \> **AutoPilot**。
  
2. 在 [ **AutoPilot** ] 頁面上，選擇 [**設定檔**] 索引標籤 \> **建立設定檔**。
    
3. 在 [**建立設定檔**] 頁面上，輸入設定檔的名稱，以協助您識別，例如「行銷」。 開啟您想要的設定，然後選擇 [**儲存**]。 如需 AutoPilot 設定檔設定的詳細資訊，請參閱[關於 AutoPilot 設定檔設定](autopilot-profile-settings.md)。
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>將設定檔套用到裝置

在您建立設定檔之後，您可以將它套用至裝置或裝置群組。 您可以在[逐步指南](add-autopilot-devices-and-profile.md)中挑選現有的設定檔，並將其套用至新裝置，或取代裝置或裝置群組的現有設定檔。 
  
1. 在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤。 
    
2. 選取裝置名稱旁邊的核取方塊，然後在 [**裝置**] 面板中，從 [**已指派的設定檔**] 下拉式清單中選擇設定檔 \> ** **。
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>編輯、刪除或移除設定檔

一旦為裝置指派設定檔後，即使您已將裝置提供給使用者，您仍可更新設定檔。當裝置連線到網際網路時，它會在設定程序期間下載您的最新版設定檔。如果使用者將其裝置還原為其原廠預設設定，裝置會將最新更新再次下載到您的設定檔。 
  
### <a name="edit-a-profile"></a>編輯設定檔

1. 在 [**準備 Windows** ] 頁面上，選擇 [**設定檔**] 索引標籤。 
    
2. 選取裝置名稱旁邊的核取方塊，然後在 [**設定檔**] 面板中，更新任何可用的設定 \> **儲存**。
    
    如果您在使用者將裝置連線到網際網路之前這麼做，設定檔則會套用到設定程序。
    
### <a name="delete-a-profile"></a>刪除設定檔

1. 在 [**準備 Windows** ] 頁面上，選擇 [**設定檔**] 索引標籤。 
    
2. 選取裝置名稱旁邊的核取方塊，然後在 [**設定檔**] 面板中，選取 [**刪除設定檔** \> **儲存**]。
    
    當您刪除設定檔時，會移除單一裝置或一組裝置中的獲派設定檔。
    
### <a name="remove-a-profile"></a>移除設定檔

1. 在 [**準備 Windows** ] 頁面上，選擇 [**裝置**] 索引標籤。 
    
2. 選取裝置名稱旁邊的核取方塊，然後在 [**裝置**] 面板中，從 [**已指派的設定檔**] 下拉式清單中選擇 [**無**] \> ** **。
    
