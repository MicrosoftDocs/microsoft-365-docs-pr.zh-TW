---
title: 為 Windows 裝置上的 Office 2013 啟用新式驗證
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 瞭解如何設定登錄機碼，以便為已安裝 Microsoft Office 2013 的裝置啟用新式驗證。
ms.openlocfilehash: f803cf9a30be63e71ef3c4293d0d1ba5b2355e75
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580831"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>為 Windows 裝置上的 Office 2013 啟用新式驗證

若要為已安裝 Office 2013 的任何 Windows 裝置啟用新式驗證，您必須先設定專用登錄機碼。
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>為 Office 2013 用戶端啟用新式驗證

> [!NOTE]
> Office 2016 用戶端已啟用新式驗證，您無需為 Office 2016 設定登錄機碼。 
  
若要針對已安裝 Microsoft Office 2013、且執行 Windows 的任何裝置啟用新式驗證 (比如膝上型電腦和平板電腦)，您必須先設定下列登錄機碼。您必須在每部要啟用新式驗證的裝置上設定機碼：
  
|**登錄機碼**|**Type**|**Value** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
設定登錄機碼之後，您可以將 Office 2013 裝置應用程式設定為使用 [多重要素驗證 (MFA) ](set-up-multi-factor-authentication.md) 搭配 Microsoft 365。 
  
如果您目前使用任何用戶端 App 登入，您就必須在登出後再次登入，變更才會生效。否則，在 ADAL 識別建立之前，您將無法使用 MRU 和漫遊設定。
  
## <a name="disable-modern-authentication-on-devices"></a>停用裝置上的新式驗證

若要停用裝置上的新式驗證，請在裝置上設定下列登錄機碼：
  
|**登錄機碼**|**Type**|**Value**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-articles"></a>相關文章
[使用第二種驗證方式登入 Office 2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[Outlook 會提示輸入密碼，而不使用新式驗證連線到 Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)

