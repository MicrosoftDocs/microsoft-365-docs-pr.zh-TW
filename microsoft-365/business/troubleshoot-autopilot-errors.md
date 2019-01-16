---
title: 針對自動駕駛裝置錯誤進行疑難排解
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 了解如何疑難排解自動駕駛儀上裝置檔案錯誤。
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866299"
---
# <a name="troubleshoot-autopilot-device-errors"></a>針對自動駕駛裝置錯誤進行疑難排解

## <a name="device-file-error-messages"></a>裝置檔案錯誤訊息

以下資訊之錯誤的一些您可能會看到時使用 Microsoft 365 Business 中的自動駕駛儀上裝置檔案。 
  
|**錯誤碼**|**若要嘗試修復**|
|:-----|:-----|
|無效的要求主體  <br/> |此錯誤發生少，如果您看到此錯誤，請嘗試操作一次。  <br/> |
|裝置硬體雜湊值不正確。  <br/> |如果您看到此錯誤，就表示您提供一個裝置硬體雜湊您 CSV 檔案中的值不正確。首先，確認已正確輸入值。如果您認為的值是正確的但仍發生此錯誤，請將您的硬體廠商尋求協助。  <br/> |
|指派給另一個承租人的裝置  <br/> |如果您看到此錯誤，就表示您 CSV 檔案中提供的序號或一或多個裝置的產品金鑰的值不正確。首先，確認已正確輸入值。如果您認為的值是正確的但仍發生此錯誤，請將您的硬體廠商尋求協助。  <br/> |
|CSV 檔案包含無效的序號或產品金鑰  <br/> |如果您看到此錯誤用意是註冊 tyring 裝置已經註冊其他組織所。若要修正此問題，請將您的硬體廠商尋求協助。  <br/> |
|使用自動駕駛儀上安裝程式不是支援此裝置  <br/> | 此錯誤表示裝置不符合自動駕駛儀上部署需求。裝置必須符合下列需求：  <br/>  Windows 10 版本 1703 或更新版本。  <br/>  新裝置尚未執行過 Windows 全新體驗設定。  <br/> |
|找不到裝置  <br/> |此錯誤表示 CSV 檔案中的一或多個裝置未註冊於您的組織。若要修正此問題，請將您的硬體廠商尋求協助。  <br/> |
   
