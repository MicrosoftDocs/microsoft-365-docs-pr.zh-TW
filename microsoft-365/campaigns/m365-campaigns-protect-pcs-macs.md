---
title: 保護未受管理的 Windows 10 PC 和 Mac
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 使用 Microsoft 365 來保護非受管理或附帶的裝置 (BYOD) 。
ms.openlocfilehash: 40e94e2f961ab34827de4ce5e43e100af53a7340
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227496"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>保護未受管理的 Windows 10 PC 和 Mac

您可以在 Microsoft Intune 中登記 Windows 10 pc 和 mac，這樣可讓您在存取環境中的資料之前確保其健康和安全。 不過，許多的行銷活動和小型企業包含的人員會將自己的裝置 (BYOD) ，而不會由組織管理。 針對這些未受管理的電腦和 Mac，請使用本文，以確保已設定最基本的安全性功能。

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>保護執行 Windows 10 或 Mac 的電腦

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
如果您的 Windows 10 電腦或 Mac 不是由您的組織所管理，請務必設定這些安全性功能。

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**開啟裝置加密**<p>

您可以在大量的 Windows 裝置上使用裝置加密，並以加密的方式協助保護您的資料。 如果您開啟裝置加密，只有經過授權的人員才能存取您的裝置和資料。 如需指示，請參閱 [開啟裝置加密](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 。

 如果裝置無法使用裝置加密，您可以改為開啟標準 [BitLocker 加密](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 。 Windows 10 家用版版上無法使用 (BitLocker。 )  

**使用 Windows 安全性保護您的裝置**<p>
如果您有 Windows 10，您會使用 Windows 安全性獲得最新的病毒防護。 當您第一次開始 Windows 10 時，Windows 安全性會開啟並積極協助您掃描惡意程式碼 (惡意軟體) 、病毒及安全性威脅，以保護您的電腦。 Windows 安全性會使用即時保護來掃描您在電腦上下載或執行的所有專案。

Windows Update 會自動下載 Windows 安全性更新，以協助您保持電腦的安全，並保護其不受威脅。

如果您有舊版的 Windows，而且正在使用 Microsoft Security Essentials，最好移至 Windows 安全性。 如需詳細資訊，請參閱[使用 Windows 安全性協助保護我的裝置](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)。

**開啟 Windows 防火牆**<p>
即使已開啟另一個防火牆，您還是應該無條件執行 Windows 防火牆。 關閉 Windows 防火牆可能會讓您的裝置 (和網路，如果您有一個) 更容易受到未授權的存取。 請參閱[開啟或關閉 Windows 防火牆](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)以取得指示。

## <a name="mac"></a>[Mac](#tab/Mac)

**使用 FileVault 來加密您的 Mac 磁片**<p>
磁片加密可在裝置遺失或遭竊時保護資料。 FileVault 完整磁片加密可協助防止未經授權的存取您的開機磁片上的資訊。 如需相關指示，請參閱 [Use FileVault to a On Mac on startup disk](https://support.apple.com/HT204837) 。

**保護您的 mac 免受惡意程式碼攻擊**<p>
Microsoft 建議您在 Mac 上安裝及使用可靠的防毒軟體。 如需挑選清單，請參閱下列文章： [最佳 Mac 防病毒 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。

您也可以只從可靠來源使用軟體，以降低惡意程式碼的風險。 安全性 & 隱私權喜好設定可讓您指定 Mac 上所安裝之軟體的來源。 如需詳細資訊，請參閱 [保護您的 Mac 免受惡意](https://support.apple.com/kb/PH25087)代碼。

**開啟防火牆保護**<p>
當您連線至網際網路或網路時，可使用防火牆設定來保護您的 Mac 免受其他電腦所初始化的有害連絡人。 若沒有此保護，您的 Mac 可能會更容易遭到未經授權的存取。 如需相關指示，請參閱 [相關應用程式防火牆](https://support.apple.com/HT201642) 。
