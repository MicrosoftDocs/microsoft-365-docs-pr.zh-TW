---
title: 疑難排解 Microsoft Defender ATP for Mac 的授權問題
description: 疑難排解 Microsoft Defender ATP for Mac 中的授權問題。
keywords: microsoft、defender、atp、mac、效能
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689110"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>疑難排解 macOS 上的 Microsoft Defender for Endpoint 的授權問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [macOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

當您在 macOS 和[手動部署](mac-install-manually.md)測試或概念證明 (PoC) 時，若要透過[Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) ，您可能會收到下列錯誤：

![授權的圖像錯誤](images/no-license-found.png)

**消息：** 

找不到授權

好像您的組織沒有 Microsoft 365 企業版訂閱的授權。

請與您的系統管理員聯繫以取得協助。

**原因：** 

您已在 macOS 套件 ( 「下載安裝套件」上部署及（或）安裝 Microsoft Defender for Endpoint ) 但是您可能已執行設定腳本 ( 「下載上架套件」 ) 。

**解決 方案：**

遵循下列所述的 MicrosoftDefenderATPOnboardingMacOs.py 指示： [Client configuration](mac-install-manually.md#client-configuration)

