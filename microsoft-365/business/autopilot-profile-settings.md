---
title: 關於 AutoPilot 設定檔的設定
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 設定檔可協助您控制如何取得使用者裝置上安裝 Windows。 設定檔包含預設和選擇性的設定，例如略過 Cortana 安裝。
ms.openlocfilehash: 912a24e3d458986a4bcf7dcf903f80211996aca2
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38321778"
---
# <a name="about-autopilot-profile-settings"></a>關於 AutoPilot 設定檔的設定

## <a name="autopilot-profile-settings"></a>AutoPilot 設定檔設定

您可以使用 AutoPilot 設定檔來控制使用者裝置上安裝 Windows 的方式。 設定檔包含下列設定值。
  
 **AutoPilot 預設功能 （必要），就會自動設定：**
  
|**設定**|**描述**|
|:-----|:-----|
|略過 Cortana、 OneDrive 及 OEM 註冊  <br/> |略過 Cortana 與個人的 OneDrive 等消費者應用程式的安裝。 裝置使用者，只要使用者在裝置上的本機系統管理員，才能安裝這些更新。 因為將會由 Microsoft 365 商務版管理裝置，會略過的原始的製造商註冊。  <br/> |
|登入您的公司品牌的經驗  <br/> |如果貴公司有[新增公司商標至 Office 365 登入] 頁面上](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)，裝置使用者會收到該經驗，當登入。  <br/> |
|MDM 自動註冊以設定 AAD 帳戶。  <br/> |將會由 Azure Active Directory 管理使用者身分識別，使用者將登入 Windows 和 Office 365 使用其 Microsoft 365 商務版認證。  <br/> |
   
 **選用的設定：**
  
|**設定**|**描述**|
|:-----|:-----|
|略過的隱私權設定 （預設為關閉）  <br/> |如果此選項設為**上**，裝置使用者會看到 [授權合約的裝置和 Windows 當他或她第一次登入。  <br/> |
|不允許使用者成為本機系統管理員  <br/> |如果此選項設為 [**開啟**，裝置使用者將無法安裝任何個人的應用程式，例如 Cortana。<br/> |
   
