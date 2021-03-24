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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059476"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>疑難排解適用于 Mac 的 Microsoft Defender for Endpoint 的授權問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [Mac 版端點的 Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

當您要透過 [Microsoft Defender For Mac](microsoft-defender-endpoint-mac.md) 和 [手動部署](mac-install-manually.md) 測試或概念證明 (PoC) 時，您可能會收到下列錯誤：

![授權的圖像錯誤](images/no-license-found.png)

**消息：** 

找不到授權

好像您的組織沒有 Microsoft 365 企業版訂閱的授權。

請與您的系統管理員聯繫以取得協助。

**原因：** 

您已為 macOS 套件部署和/或安裝 Microsoft Defender for Endpoint ( "下載安裝套件" ) 但是您可能已執行設定腳本 ( "下載上架套件" ) 。

**解決 方案：**

遵循下列所述的 MicrosoftDefenderATPOnboardingMacOs.py 指示： [Client configuration](mac-install-manually.md#client-configuration)

