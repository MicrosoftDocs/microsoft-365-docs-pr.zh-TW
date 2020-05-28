---
title: 關於 AutoPilot 設定檔的設定
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 設定檔可協助您控制 Windows 在使用者裝置上安裝的方式。 設定檔包含略過 Cortana 安裝等預設和選用設定。
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401027"
---
# <a name="about-autopilot-profile-settings"></a>關於 AutoPilot 設定檔的設定

## <a name="autopilot-profile-settings"></a>AutoPilot 設定檔設定

您可以使用 AutoPilot 設定檔來控制在使用者裝置上安裝 Windows 的方式。 設定檔包含下列設定值。
  
 **會自動設定 AutoPilot 預設功能（必要）：**
  
|**設定**|**描述**|
|:-----|:-----|
|略過 Cortana、OneDrive 及 OEM 註冊  <br/> |會略過安裝使用中的應用程式，例如 Cortana 和個人 OneDrive。 只要使用者是裝置上的本機系統管理員，裝置使用者便可以安裝這些更新。 已略過原始製造商註冊，因為裝置將會受到 Microsoft 365 商務版 Premium 的管理。  <br/> |
|使用您的公司品牌登入經驗  <br/> |如果貴公司已[將公司商標新增至 Microsoft 365 登入頁面](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page)，裝置使用者會在登入時取得該經驗。  <br/> |
|MDM 使用已設定的 AAD 帳戶進行自動註冊。  <br/> |使用者身分識別將由 Azure Active Directory 管理，使用者會以 Microsoft 365 商務版認證登入 Windows 和 Microsoft 365。  <br/> |
   
 **選用的設定：**
  
|**設定**|**描述**|
|:-----|:-----|
|略過隱私權設定（預設為關閉）  <br/> |如果此選項設定為 [**開啟**]，裝置使用者在第一次登入時，將不會看到裝置和 Windows 的授權合約。  <br/> |
|不允許使用者成為本機系統管理員  <br/> |如果此選項設定為 [**開啟**]，裝置使用者將無法安裝任何個人應用程式，例如 Cortana。<br/> |
   
