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
ms.openlocfilehash: df52d500c945275b62170ab16260f0c019340f73
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429923"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>選擇基本行動性和安全性及 Intune

Microsoft Intune 是一種獨立的產品，包含在某些 Microsoft 365 方案中，基本行動性 & 安全性是 Microsoft 365 方案的一部分。 這兩種方案都包含在各項方案中，如下表所述。

|**規劃**|**基本行動性和安全性**|**Microsoft Intune**|
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
|Microsoft 365 Eductation A1 |是|是|
|Microsoft 365 教育版 A3 |是|是|
|Microsoft 365 教育版 A5 |是|是|
|Microsoft Intune |否|是|
|企業行動性 & 安全性 E3 |否|是|
|企業行動 & 安全性 E5 |否|是|

>[!NOTE]
>如果您已經在使用 Microsoft Intune，您就無法開始使用基本行動性和安全性。

## <a name="differences-in-capabilities"></a>功能上的差異

Microsoft Intune 和內建基本行動性及安全性兩者都能讓您在組織中管理行動裝置，但功能上有一些重要差異，如下表所述。

>[!NOTE]
>您可以先設定基本行動性和安全性，然後再新增 Microsoft Intune，以在相同的 Microsoft 365 Business Standard 組織中使用 Intune 和基本行動性和安全性，管理使用者和其行動裝置。 這可讓您選擇是否要管理具有基本行動性和安全性的使用者裝置，或功能更豐富的 Intune 解決方案。 在模式中，授權指派決定裝置註冊的服務。 指派 Intune 授權以啟用僅供 Intune 使用的功能。

|**功能範圍**|**功能重點**|**基本行動性和安全性**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|裝置類型|不同的作業系統平臺及主要的管理模式變種。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac 作業系統<br/>iPad 作業系統|
|裝置合規性|設定和管理安全性原則，如裝置層級 PIN 碼鎖定和 jailbreak 偵測。 |Android 9 和更新版本裝置的限制。 如需詳細資訊，請參閱 [基本行動性和安全性的功能](capabilities.md)。|是|
|根據裝置規範的條件式存取 |防止不相容的裝置從雲端存取公司的電子郵件和資料。 |-在 Windows 10 上不受支援。<br/>-局限于控制對 Exchange Online、Sharepoint Online 和 Outlook 服務的存取。 |否|
|裝置設定  |設定裝置設定 (例如停用攝像頭) 。 |有限的設定集。如需詳細資訊，請參閱 [基本行動性和安全性的功能](capabilities.md)。 |是|
|遠端動作  |透過網際網路將命令傳送至裝置。 例如，從員工的裝置移除 Office 資料，同時保留個人資料 (停用) 。 |淘汰<br/>擦去<br/>刪除|-僅 (Windows) 重設 Autopilot<br/>- [Bitlocker 金鑰輪替](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)  僅限 Windows () <br/>- [刪除](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [停用啟用 loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)  僅 (iOS) <br/>- [全新開始](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)  僅限 Windows () <br/>- [完整掃描](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)  僅限 Windows 10 () <br/>- [尋找裝置](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)  僅 (iOS) <br/>- [遺失模式](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)  僅 (iOS) <br/>- 僅限 Windows 10 ([快速掃描](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)) <br/>- [Android 的遠端控制](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [遠端鎖定](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [重新命名裝置](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [重設密碼](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [重新開機](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)  僅限 Windows () <br/>- [退休](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>-僅更新 Windows Defender 安全性情報 (Windows) <br/>-Windows 10 PIN 碼重設 (僅限 Windows) <br/>- [擦](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [傳送自訂通知](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android、iOS、iPad 作業系統) <br/>- [同步處理裝置](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|電子郵件設定檔  |在裝置上布建原生電子郵件設定檔。 |是|是|
|WIFI 設定檔 |在裝置上布建本機 WIFI 設定檔。 |否|是|
|VPN 設定檔 |在裝置上布建本機 VPN 設定檔。 |否|是|
|MDM 應用程式管理  |部署內部企業營運應用程式，以及從應用程式存放區至使用者。 |否|是|
|行動應用程式保護  |讓您的使用者能夠使用所知道的 Office mobile 和商務營運應用程式，安全地存取公司資訊，同時也可以透過協助限制複製、剪下、貼上的動作，以及僅限受核准以取得公司資料的應用程式，以確保資料的安全性。 即使裝置並未註冊至 MDM 也可以運作。 請參閱使用 MAM 原則保護應用程式資料。 |否|是|
|Managed browser  |使用 Edge app，啟用更安全的 web 流覽功能。 |否|是|
|零觸控註冊計畫 |註冊大量公司所擁有的裝置，同時簡化使用者設定。 |否|是|
