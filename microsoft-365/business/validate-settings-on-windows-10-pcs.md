---
title: 驗證 Windows 10 PC 上的 App 保護設定
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 瞭解如何驗證 Microsoft 365 for business app protection 設定會在使用者的 Windows 10 裝置上生效。
ms.openlocfilehash: ff99b3a4fce49aebdb5c72f51e46678a7821e186
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912407"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>在 Windows 10 電腦上驗證裝置保護設定

## <a name="verify-that-windows-10-device-policies-are-set"></a>確認已設定 Windows 10 裝置原則

[設定裝置原則](protection-settings-for-windows-10-pcs.md)之後，可能需要數小時的時間，才能讓原則在使用者的裝置上生效。 您可以在使用者的裝置上查看各種 Windows 設定畫面，以確認原則是否生效。 因為使用者無法修改其 Windows 10 裝置上的 Windows Update 和 Windows Defender 防病毒設定，所以許多選項會變暗。
  
1. 移至 [ **設定**] [ \> **更新 &amp; 安全性**] [ \> **Windows 更新** \> **重新開機] 選項** ，並確認所有設定均呈現灰色。 
    
    ![所有重新開機選項都是灰色的。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. 移至 [ **設定**] [ \> **更新 &amp; 安全性**] [ \> **Windows 更新**] [ \> **高級選項** ]，確認所有設定均呈現灰色。 
    
    ![Windows 高級更新選項都是灰色的。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. 移至 [ **設定** \> **更新 &amp; 安全性**] \> **Windows 更新** \> [ **高級選項**] \> **選擇如何傳送更新**。
    
    請確認您可以看到郵件 (以紅色) 某些設定已隱藏或由您的組織管理，而且所有選項均呈現灰色。
    
    ![選擇如何傳送更新頁面表示設定已隱藏或由您的組織管理。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. 若要開啟 Windows defender 安全中心，請移至 [ **設定** \> **更新 &amp; 安全性**] \> **Windows defender** \> 按一下 [ **開啟 windows defender 安全中心** \> **病毒 &amp; 執行緒防護** \> **病毒 &amp; 防護] 設定**。 
    
5. 確認所有選項均呈現灰色。 
    
    ![[病毒和威脅防護] 設定會變暗。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>相關主題

[商務用 Microsoft 365 檔和資源](./index.yml)
  
[開始使用 Microsoft 365 for business](microsoft-365-business-overview.md)
  
[管理 Microsoft 365 for business](manage.md)
  
[設定適用於 Windows 10 電腦的裝置設定](protection-settings-for-windows-10-pcs.md)
