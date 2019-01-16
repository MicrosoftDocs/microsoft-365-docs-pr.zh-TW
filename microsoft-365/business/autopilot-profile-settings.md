---
title: 關於 AutoPilot 設定檔的設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
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
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自動駕駛儀上設定檔可協助您控制 Windows 取得安裝在使用者裝置上的方式。設定檔包含預設和選用設定 like 略過 Cortana 安裝。
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866145"
---
# <a name="about-autopilot-profile-settings"></a>關於 AutoPilot 設定檔的設定

## <a name="autopilot-profile-settings"></a>自動駕駛儀上設定檔設定

您可以控制如何 Windows 取得安裝在使用者裝置上使用自動駕駛儀上設定檔。設定檔包含下列設定值。
  
 **自動駕駛儀上預設 （必要） 的功能會自動設定：**
  
|**設定**|**描述**|
|:-----|:-----|
|略過 Cortana、 OneDrive 及 OEM 註冊  <br/> |會略過 Cortana 和個人 OneDrive 的用戶應用程式的安裝。只要他就是在裝置上的本機系統管理員裝置使用者可以安裝這些更新。原始的製造商註冊會略過裝置將變成由 Microsoft 365 Business。  <br/> |
|登入經驗與公司品牌  <br/> |如果您的公司具有[新增您的公司品牌 Office 365 登入] 頁面上](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)，裝置使用者會取得該經驗時登入。  <br/> |
|MDM 自動註冊具有設定 AAD 帳戶。  <br/> |使用者身分識別將變成由 Azure Active directory、 及使用者將會使用其 Microsoft 365 商務認證簽署至 Windows 與 Office 365。  <br/> |
   
 **選用的設定：**
  
|**設定**|**描述**|
|:-----|:-----|
|略過隱私權設定 （預設為關閉）  <br/> |如果此選項設為**在**裝置使用者不會看到裝置和 Windows 授權的合約時一次第一次登入。  <br/> |
|不允許使用者可以成為本機管理員  <br/> |如果此選項設為**在**、 裝置使用者將無法安裝任何個人的應用程式，例如 Cortana。  <br/> |
   
