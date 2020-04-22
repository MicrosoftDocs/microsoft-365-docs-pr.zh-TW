---
title: AutoPilot 裝置錯誤疑難排解
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 瞭解如何疑難排解在使用 Microsoft 365 商務版 Premium 中的 AutoPilot 裝置檔案時，可能會看到的錯誤。
ms.openlocfilehash: 0c0742e5bf17c85cedfb421cabfd87c0e2184ba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635037"
---
# <a name="troubleshoot-autopilot-device-errors"></a>AutoPilot 裝置錯誤疑難排解

## <a name="device-file-error-messages"></a>裝置檔錯誤訊息

以下是在使用 Microsoft 365 商務版 Premium 中的 AutoPilot 裝置檔案時，可能會看到的一些錯誤的相關資訊。 
  
|**錯誤碼**|**修正以嘗試**|
|:-----|:-----|
|不正確要求體  <br/> |這種錯誤應該很少發生，如果您看到此錯誤，請重試此作業。  <br/> |
|裝置的硬體雜湊值不正確。  <br/> |如果您看到此錯誤，表示您在 CSV 檔案中為一個裝置的硬體雜湊所提供的值不正確。 首先，請確認輸入的值正確。 如果您認為此值是正確的，但是此錯誤仍會發生，請向您的硬體廠商尋求協助。  <br/> |
|指派給其他租使用者的裝置  <br/> |如果您看到此錯誤，表示您在 CSV 檔案中所提供的數值是一或多個裝置的序號碼或產品金鑰不正確。 首先，請確認輸入的值正確。 如果您認為此值是正確的，但是此錯誤仍會發生，請向您的硬體廠商尋求協助。  <br/> |
|CSV 檔案包含不正確序號碼或產品金鑰  <br/> |如果您看到此錯誤，表示您嘗試註冊的裝置已由另一個組織註冊。 若要修正此錯誤，請向您的硬體廠商尋求協助。  <br/> |
|此裝置不支援使用 AutoPilot 設定  <br/> | 此錯誤表示裝置不符合 AutoPilot 部署需求。 裝置必須符合這些需求：  <br/>  Windows 10 版本 1703 或更新版本。  <br/>  尚未透過 Windows 全新體驗的新裝置。  <br/> |
|找不到裝置  <br/> |此錯誤表示您的 CSV 檔案中的一或多個裝置並未註冊至您的組織。 若要修正此問題，請向您的硬體廠商尋求協助。  <br/> |
