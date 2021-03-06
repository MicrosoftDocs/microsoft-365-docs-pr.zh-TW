---
title: 關於 AutoPilot 設定檔的設定
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578500"
---
# <a name="about-autopilot-profile-settings"></a>關於 AutoPilot 設定檔的設定

## <a name="autopilot-profile-settings"></a>AutoPilot 設定檔設定

您可以使用 AutoPilot 設定檔來控制如何在使用者裝置上安裝 Windows。 設定檔包含下列設定值。
  
 **AutoPilot 預設功能 (會自動設定必要) ：**
  
|**設定**|**描述**|
|:-----|:-----|
|略過 Cortana、OneDrive 及 OEM 註冊  <br/> |會略過安裝使用中的應用程式，例如 Cortana 和個人 OneDrive。 只要使用者是裝置上的本機系統管理員，裝置使用者便可以安裝這些更新。 因為 Microsoft 365 商務進階版會管理裝置，所以會略過原始製造商註冊。  <br/> |
|使用您的公司品牌登入經驗  <br/> |如果貴公司已[將公司署名新增至 Microsoft 365 登入] 頁面](../admin/setup/customize-sign-in-page.md)上，裝置使用者會在登入時取得該經驗。  <br/> |
|MDM 使用已設定的 AAD 帳戶進行自動註冊。  <br/> |Azure Active Directory 會管理使用者身分識別，使用者會以 Microsoft 365 商務進階版認證登入 Windows 和 Microsoft 365。  <br/> |
   
 **選用的設定：**
  
|**設定**|**描述**|
|:-----|:-----|
|預設會略過隱私權設定 (關閉)   <br/> |如果此選項設定為 [**開啟**]，裝置使用者在第一次登入時，將不會看到裝置和 Windows 的授權合約。  <br/> |
|不允許使用者成為本機系統管理員  <br/> |如果此選項設定為 [ **開啟**]，裝置使用者將無法安裝任何個人應用程式，例如 Cortana。<br/> |
