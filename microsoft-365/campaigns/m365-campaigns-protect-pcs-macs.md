---
title: 保護未受管理的 Windows 10 電腦和 Mac
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 使用 Microsoft 365 的市場活動來防禦網路釣魚和其他攻擊。
ms.openlocfilehash: 8b83fa9c145f2c17347fc4c2983c64d4003f46c8
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183254"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>保護未受管理的 Windows 10 電腦和 Mac

您可以使用 Microsoft Intune 來管理 Windows 10 電腦和 Mac, 這可讓您在存取環境中的資料之前, 先確保這些電腦的健康和安全。 不過, 許多行銷活動和小型企業包含的人員會攜帶自己的裝置 (byod), 而該組織不會管理這些裝置。 針對這些未受管理的電腦和 Mac, 請使用本文來確保設定最基本的安全性功能。 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>保護執行 Windows 10 或 Mac 版的電腦

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
如果您的組織不會管理您的 Windows 10 電腦或 Mac, 請務必設定這些安全性功能。

## <a name="windows-10tabwindows10"></a>[Windows 10](#tab/Windows10)
**開啟裝置加密**<p>

裝置加密在各種 Windows 裝置上都可以使用, 並可加密資料以協助保護您的資料。 如果您開啟裝置加密, 只有授權的個人才能存取您的裝置和資料。 請參閱[開啟裝置加密](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption)以取得指示。

 如果裝置上無法使用裝置加密, 您可以改為開啟標準的[BitLocker 加密](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption)。 (BitLocker 在 Windows 10 首頁版上無法使用。) 



**使用 Windows 安全性保護您的裝置**<p>
如果您有 Windows 10, 您可以使用 Windows 安全性取得最新的病毒防護。 當您第一次啟動 Windows 10 時, Windows 安全性就會開啟, 並積極協助您掃描惡意程式碼 (惡意軟體)、病毒和安全性威脅, 以保護您的電腦。 Windows 安全性使用即時保護來掃描您下載或在您的電腦上執行的所有專案。

Windows Update 會自動下載 Windows 安全性的更新, 以協助保護您的電腦安全性並防止威脅。

如果您有舊版的 Windows, 且使用 Microsoft 安全性基本版, 則最好移至 Windows 安全性。 如需詳細資訊, 請參閱[協助保護我的裝置與 Windows 安全性](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security)。

**開啟 Windows 防火牆**<p>
即使已開啟另一個防火牆, 您也應該始終執行 Windows 防火牆。 關閉 Windows 防火牆可能會讓您的裝置 (和您的網路) 更容易受到未經授權的存取。 請參閱[開啟或關閉 Windows 防火牆](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)以取得指示

## <a name="mactabmac"></a>[Mac](#tab/Mac)
**使用 FileVault 來加密您的 Mac 磁片**<p>
磁片加密會在裝置遺失或被盜時, 保護資料。 FileVault 完整磁片加密有助於防止未經授權的存取啟動磁片上的資訊。 如需相關指示, 請參閱[使用 FileVault 加密 Mac 上的開機磁片](https://support.apple.com/HT204837)。

**保護 mac 免遭惡意程式碼**<p>
Microsoft 建議您在 Mac 上安裝和使用可靠的防毒軟體。 如需選項清單, 請參閱下列文章:[最佳 Mac 防病毒 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。

您也可以只從可靠的來源使用軟體, 來減少惡意程式碼的風險。 安全性 & 隱私權偏好設定中的設定可讓您指定 Mac 上所安裝之軟體的來源。 如需詳細資訊, 請參閱[保護您的 Mac 免受惡意軟體的攻擊](https://support.apple.com/kb/PH25087)。

**開啟防火牆保護**<p>
當您連線至網際網路或網路時, 使用防火牆設定來保護您的 Mac 免受其他電腦所初始化的不需要連絡人。 若沒有此保護, 您的 Mac 可能更容易受到未經授權的存取。 如需相關指示, 請參閱[相關應用程式防火牆](https://support.apple.com/HT201642)。
