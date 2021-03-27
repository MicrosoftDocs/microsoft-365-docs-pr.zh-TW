---
title: 疑難排解 Microsoft Defender for Mac 的性能問題
description: 疑難排解 Microsoft Defender for Mac 中的效能問題。
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
ms.openlocfilehash: 87190d9e0bb62d42642374bd7c9f6f3acad3c80a
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379380"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>疑難排解 Microsoft Defender for Mac 的性能問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [Mac 版適用於端點的 Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主題提供一些一般步驟，可用來縮小 Microsoft Defender for Mac 之相關的效能問題。

即時保護 (RTP) 是適用于 Mac 的 Microsoft Defender 端點的功能，可持續監視和保護您的裝置免受威脅。 它包含檔案和程式監視及其他試探法。

視您執行的應用程式和裝置特性而定，當您執行 Microsoft Defender for Mac 時，可能會遇到效能效能。 特別是，透過簡短的 timespan 存取許多資源的應用程式或系統進程，可能會導致 Microsoft Defender for Mac 中的效能問題。

下列步驟可用於疑難排解及緩解下列問題：

1. 使用下列其中一種方法來停用即時保護，並觀察效能是否提高。 這種方法可協助縮小 Microsoft Defender for Mac 是否對效能問題造成的影響。

    如果您的裝置不是由您的組織管理，則可以使用下列其中一個選項停用即時保護：

    - 從使用者介面。 開啟 Mac 版的 Microsoft Defender 端點，並流覽至 [ **管理設定**]。

      ![管理即時保護螢幕擷取畫面](images/mdatp-36-rtp.png)

    - 從終端。 基於安全性的考慮，此作業需要提升。

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    如果您的裝置是由您的組織管理，您的系統管理員可以使用 [Microsoft Defender For Mac 的設定偏好設定](mac-preferences.md)中的指示，停用即時保護。

2. 開啟 Finder，並流覽至 **應用程式**  >  **公用程式**。 開啟 **活動監視器** 並分析哪些應用程式正在使用您系統上的資源。 典型範例包括軟體 updaters 及編譯器。

3. 針對影響效能問題及重新啟用即時保護的處理常式或磁片位置，針對 Mac 設定 Microsoft Defender for Mac 的排除專案。

    如需詳細資訊，請參閱 [設定及驗證 Microsoft Defender For Mac 的排除](mac-exclusions.md) 專案。
