---
title: 評估網路保護
description: 測試其保護的常見案例，以查看網路保護的運作方式。
keywords: 網路保護、手段、惡意網站、ip、網域、網域、評估、測試、示範
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 03d05966401c8f3a8bdcec413e85c9a6d2a3ec5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926568"
---
# <a name="evaluate-network-protection"></a>評估網路保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[網路保護](network-protection.md) 可協助防止員工使用任何應用程式來存取可能會在網際網路上主控網路釣魚詐騙、入侵和其他惡意內容的危險網域。

本文可協助您評估網路保護，只要啟用該功能並引導您進行測試網站。 這項評估文章中的網站不是惡意的。 他們已特別建立了假裝為惡意的網站。 網站會複製使用者在訪問惡意網站或網域時會發生的行為。

> [!TIP]
> 您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender Testground 網站，以查看其他保護功能的運作方式。

## <a name="enable-network-protection-in-audit-mode"></a>在稽核模式中啟用網路保護

在稽核模式中啟用網路保護，以查看已封鎖的 IP 位址和網域。 您可以確定不會影響企業營運的應用程式，或瞭解封鎖發生的頻率。

1. 在 [開始] 功能表中輸入 **powershell** ，以滑鼠右鍵按一下 **Windows PowerShell** 並選取 [以 **系統管理員身分執行**]
2. 輸入下列 Cmdlet：

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>造訪 (假冒) 惡意網域

1. 開啟 Internet Explorer、Google Chrome 或您選擇的任何其他瀏覽器。

1. 請移至 [https://smartscreentestratings2.net](https://smartscreentestratings2.net)。

將會允許網路連線，並且會顯示測試郵件。

![通知連線已封鎖的範例通知：您的 IT 系統管理員造成 Windows 安全性封鎖此網路連接。 請與您的 IT 問訊台聯繫。](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>在 Windows 事件檢視器中查看網路保護事件

若要查看已封鎖的應用程式，請在 Microsoft Windows Windows 中開啟事件檢視器並篩選事件識別碼1125。 下表列出所有網路保護事件。

| 事件識別碼 | 提供/來源 | 描述 |
|-|-|-|
|5007 | Windows Defender (操作)  | 設定變更時的事件 |
|1125 | Windows Defender (操作)  | 審核網路連接時的事件 |
|1126 | Windows Defender (操作)  | 封鎖網路連接時的事件 |

## <a name="see-also"></a>另請參閱

* [網路保護](network-protection.md)
* [啟用網路保護](enable-network-protection.md)
* [疑難排解網路保護](troubleshoot-np.md)
