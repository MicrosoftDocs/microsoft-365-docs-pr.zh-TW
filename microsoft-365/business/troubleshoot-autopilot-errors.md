---
title: AutoPilot 裝置錯誤疑難排解
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 了解如何針對自動駕駛裝置檔案錯誤進行疑難排解。
ms.openlocfilehash: 8390f695a3e11386ae2617da4061bed1d8214375
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594201"
---
# <a name="troubleshoot-autopilot-device-errors"></a>AutoPilot 裝置錯誤疑難排解

## <a name="device-file-error-messages"></a>裝置檔案錯誤訊息

在某些錯誤的以下資訊您可能會看到時使用 Microsoft 365 商務版中的自動駕駛裝置檔案。 
  
|**錯誤碼**|**若要嘗試修正**|
|:-----|:-----|
|無效的要求本體  <br/> |應該很少，會發生此錯誤如果您看到這項錯誤，請再操作一次。  <br/> |
|裝置硬體雜湊值不正確。  <br/> |如果您看到這項錯誤，就表示您提供的一部裝置硬體雜湊 CSV 檔案中的值不正確。 首先，確認已正確輸入值。 如果您認為的值正確，但仍然發生此錯誤，請將您的硬體廠商尋求協助。  <br/> |
|指派給另一個租用戶的裝置  <br/> |如果您看到這項錯誤，就表示您所提供的序號或產品金鑰的一或多個裝置 CSV 檔案中的值不正確。 首先，確認已正確輸入值。 如果您認為的值正確，但仍然發生此錯誤，請將您的硬體廠商尋求協助。  <br/> |
|CSV 檔案包含無效的序號或產品金鑰  <br/> |如果您看到這項錯誤，就表示您嘗試註冊的裝置已登錄的另一個組織。 若要修正此錯誤，請將您的硬體廠商尋求協助。  <br/> |
|使用 AutoPilot 設定不是支援此裝置  <br/> | 這個錯誤表示裝置不符合 AutoPilot 部署需求。 裝置必須符合這些需求：  <br/>  Windows 10 版本 1703 或更新版本。  <br/>  新裝置尚未透過 Windows 現成可用的體驗。  <br/> |
|找不到裝置  <br/> |這個錯誤表示您的 CSV 檔案中的一或多個裝置未登錄至您的組織。 若要修正此問題，請將您的硬體廠商尋求協助。  <br/> |
