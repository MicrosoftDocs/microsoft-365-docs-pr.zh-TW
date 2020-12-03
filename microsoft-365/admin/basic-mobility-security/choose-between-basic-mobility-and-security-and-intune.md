---
title: 選擇基本行動性和安全性及 Intune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
search.appverid:
- MET150
description: 基本行動性和安全性是 Microsoft 365 方案的一部分。
ms.openlocfilehash: 8724b3dccbdb5949190ceda4b804b9f1f2a5d4b2
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561492"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>選擇基本行動性和安全性或 Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) 是一種獨立的產品，包含在某些 microsoft 365 方案中，基本行動性和安全性都是 Microsoft 365 方案的一部分。 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>基本行動性和安全性及 Intune 的可用性
 
基本行動性和安全性及 Intune 都包含在各種方案中，如下表所述。

| 方案 | 基本行動性和安全性 | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 Apps|是|否|
|Microsoft 365 商務基本版|是|否|
|Microsoft 365 商務標準版|是|否|
|Office 365 E1 |是|否|
|Office 365 E3 |是|否|
|Office 365 E5 |是|否|
|Microsoft 365 商務進階版 |是|是|
|Microsoft 365 Firstline 3 |是|是|
|Microsoft 365 企業版 E3 |是|是|
|Microsoft 365 企業版 E5 |是|是|
|Microsoft 365 教育版 A1 |是|是|
|Microsoft 365 教育版 A3 |是|是|
|Microsoft 365 教育版 A5 |是|是|
|Microsoft Intune |否|是|
|企業行動性 & 安全性 E3 |否|是|
|企業行動 & 安全性 E5 |否|是|

>[!NOTE]
>如果您已經在使用 Microsoft Intune，您就無法開始使用基本行動性和安全性。

 如需詳細資訊，請參閱 [Microsoft 365 和 Office 365 平臺服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 

## <a name="differences-in-capabilities"></a>功能上的差異

Microsoft Intune 和內建基本行動性及安全性兩者都能讓您在組織中管理行動裝置，但功能上有一些重要差異，如下表所述。

>[!NOTE]
>您可以 *先設定基本行動性和安全性，然後再新增 Microsoft Intune，* 以在相同的 Microsoft 365 Business Standard 組織中使用 Intune 和基本行動性和安全性，管理使用者和其行動裝置。 這可讓您選擇基本行動性和安全性，或功能更豐富的 Intune 解決方案。 指派 Intune 授權以啟用 Intune 功能。

| 功能範圍 | 功能重點 | 基本行動性和安全性 | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|裝置類型|管理不同的作業系統平臺及主要管理模式變化。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS、iPad 作業系統|
|裝置合規性|設定和管理安全性原則，如裝置層級 PIN 碼鎖定和 jailbreak 偵測。 |Android 9 和更新版本裝置的限制。 請參閱 [詳細資料](capabilities.md)。 |是|
|根據裝置規範的條件式存取 |防止不相容的裝置從雲端存取公司的電子郵件和資料。 |在 Windows 10 上不受支援。<br/>限制控制對 Exchange Online、SharePoint 線上和 Outlook 的存取。 |是 |
|裝置設定  |設定裝置設定 (例如，停用攝像頭) |裝置合規性|設定和管理安全性原則，如裝置層級 PIN 碼鎖定和 jailbreak 偵測。 |Android 9 和更新版本裝置的限制。 請參閱 [詳細資料](capabilities.md)。 |是|
 |有限的設定集。 |是|
|電子郵件設定檔  |在裝置上布建原生電子郵件設定檔。 |是|是|
|WiFi 設定檔 |在裝置上布建原生 WiFi 設定檔。 |否|是|
|VPN 設定檔 |在裝置上布建本機 VPN 設定檔。 |否|是|
|MDM 應用程式管理 |部署內部企業營運應用程式，以及從應用程式存放區至使用者。 |否|是|
|媽媽 |您的使用者可以使用 Office mobile 和商務營運應用程式來安全地存取公司資訊，方法是協助限制複製、剪下、貼上及另存為的動作，僅限認可公司資料的應用程式。 |否|是|
|Managed browser  |使用 Edge app，啟用更安全的 web 流覽功能。 |否|是|
|零接觸註冊計畫 Autopilot)  |註冊大量公司所擁有的裝置，同時簡化使用者設定。 |否|是|
|||

除了上述表格中所列的功能之外，基本行動性和安全性及 Intune 皆包含一組遠端動作，可透過網際網路將命令傳送至裝置。 例如，您可以從員工的裝置移除 Office 資料，同時保留個人資料 (停用) 、從員工裝置移除 Office app (擦除) 或將裝置重設為其出廠設定 (完全擦除) 。 

基本行動性和安全性遠端動作包括淘汰、擦除和完全清除。 如需基本行動性及安全性動作的詳細資訊，請參閱 [基本行動性和安全性的功能](capabilities.md)。

使用 Intune 時，您可以執行下列一組動作：

-   Autopilot 僅限 Windows (重設
-  [Bitlocker 金鑰輪替](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)  僅限 Windows () 
-  [使用擦除、淘汰或手動 unenrolling 裝置](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [停用啟用 loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)  僅 (iOS) 
-  [全新開始](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)  僅限 Windows () 
- [完整掃描](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)  僅限 Windows 10 () 
- [尋找裝置](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)  僅 (iOS) 
- [遺失模式](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)  僅限 (iOS) -[快速掃描](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) (僅限 Windows 10) 
- [Android 的遠端控制](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [遠端鎖定](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [重新命名裝置](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  僅限 Windows) [重設密碼](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)[重新開機](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (
-  僅 (Windows) 更新 Windows Defender 安全性情報
-  Windows 10 PIN 碼重定 (僅限 Windows) 
-  [傳送自訂通知](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android、iOS、iPad 作業系統) 
-  [同步處理裝置](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

如需 Intune 動作的詳細資訊，請參閱 [Microsoft Intune 檔](https://docs.microsoft.com/mem/intune/)。
