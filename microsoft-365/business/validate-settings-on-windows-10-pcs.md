---
title: 驗證 Windows 10 PC 上的 App 保護設定
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何驗證 Windows 10 裝置中的 Microsoft 365 商務應用程式保護設定。
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866286"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>驗證 Windows 10 Pc 上的裝置保護設定

## <a name="verify-that-windows-10-device-policies-are-set"></a>確認 Windows 10 裝置原則的設定

之後您[設定裝置原則](protection-settings-for-windows-10-pcs.md)，它可能需要幾個小時才會影響使用者的裝置原則。您可以確認原則的使用者的裝置上查看 \\servername\share\spbr 各種 Windows 設定畫面萬一效果。使用者將無法修改其 Windows 10 裝置上的 Windows Update 及 Windows 防禦者防毒設定，因為這些選項的許多將會顯示成灰色。
  
1. 移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **重新啟動選項**並確認所有設定的都灰色。 
    
    ![重新啟動的所有選項的都灰色。](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. 移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **進階選項**，並確認所有設定的都灰色。 
    
    ![Windows Advanced 更新選項是所有顯示成灰色。](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. 移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **進階選項** \> **選擇更新傳遞的方式**。
    
    確認您可以看到的訊息 （以紅色） 和部分設定都是隱藏或管理您的組織的所有選項會顯示成都灰色。
    
    ![選擇更新傳遞的方式] 頁面上會指出設定都是隱藏或由組織管理。](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. 若要開啟 [Windows 防禦者安全性中心，移至 [**設定** \> **更新&amp;安全性** \> **Windows 防禦者**\>按一下 [**開啟 Windows 防禦者安全性中心** \> **病毒&amp;執行緒保護** \> **病毒&amp;威脅保護設定**。 
    
5. 確認所有選項的都灰色。 
    
    ![病毒和威脅保護設定被灰色。](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>相關主題

[Microsoft 365 商務版文件和資源](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[開始使用 Microsoft 365 商務版](microsoft-365-business-overview.md)
  
[管理 Microsoft 365 商務版](manage.md)
  
[設定適用於 Windows 10 電腦的裝置設定](protection-settings-for-windows-10-pcs.md)
  

