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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何確認 Microsoft 365 商務版的 app 保護設定所需使用者的 Windows 10 裝置上的效果。
ms.openlocfilehash: 47977f8d79eb6dbb2f4d087af8f8ad7da4313c61
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560673"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>驗證 Windows 10 電腦上的裝置保護設定

## <a name="verify-that-windows-10-device-policies-are-set"></a>請確認已設定 Windows 10 裝置原則

之後您[設定裝置原則](protection-settings-for-windows-10-pcs.md)，可能會佔用的原則至使用者的裝置上生效的幾個小時。 您可以確認原則所需的效果，來查看使用者的裝置上的各種 Windows 設定畫面。 因為使用者無法修改其 Windows 10 裝置上的 Windows 更新] 和 [Windows Defender 防毒軟體設定，有許多選項將會變為灰色。
  
1. 移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **重新啟動選項**，並確認所有設定呈現都灰色。 
    
    ![重新啟動的所有選項會都變為灰色。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. 移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **進階選項]** ，並確認所有設定呈現都灰色。 
    
    ![Windows Advanced 更新選項所有會變為灰色。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. 移至 [**設定** \> **更新&amp;安全性** \> **Windows Update** \> **進階選項** \> **選擇更新傳送的方式**。
    
    確認您可以看到的訊息 （以紅色），某些設定都是隱藏或受管理的組織，並且會變為灰色，所有選項。
    
    ![選擇 [更新傳送的方式設定都是隱藏或由組織管理] 頁面上會指示。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. 若要開啟 [Windows Defender 資訊安全中心，移至 [**設定** \> **更新&amp;安全性** \> **Windows Defender** \>按一下 [**開啟 Windows defender 資訊安全中心** \> **病毒&amp;執行緒保護** \> **病毒&amp;威脅保護設定**。 
    
5. 確認所有選項呈現都灰色。 
    
    ![病毒和威脅保護設定會變為灰色。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>相關主題

[Microsoft 365 商務版文件和資源](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[開始使用 Microsoft 365 商務版](microsoft-365-business-overview.md)
  
[管理 Microsoft 365 商務版](manage.md)
  
[設定適用於 Windows 10 電腦的裝置設定](protection-settings-for-windows-10-pcs.md)
  

