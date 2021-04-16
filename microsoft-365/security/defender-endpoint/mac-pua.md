---
title: 使用 Microsoft Defender for Mac 偵測和封鎖可能有害的應用程式
description: 使用 Microsoft Defender for Mac (PUA) 偵測並封鎖可能有害的應用程式。
keywords: microsoft、defender、atp、mac、pua、pus
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
ms.openlocfilehash: 93462b37c9150f1e38239a0ca70b96ad8d07830f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862220"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上使用 Microsoft Defender for Endpoint 偵測並封鎖可能有害的應用程式

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


MacOS 上的 Microsoft Defender for Endpoint (PUA) 保護功能可偵測並封鎖您網路中端點上的 PUA 檔案。

這些應用程式不會被視為病毒、惡意程式碼或其他類型的威脅，但是可能會對對其效能或使用不良影響的端點執行動作。 PUA 也可以參考被視為具有不良信譽的應用程式。

這些應用程式可能會增加網路受到惡意程式碼感染的風險，使惡意程式碼感染難以識別，而且可以在清理應用程式時浪費 IT 資源。

## <a name="how-it-works"></a>運作方式

MacOS 上的 Microsoft Defender for Endpoint 可以偵測及報告 PUA 檔案。 當以封鎖模式設定時，PUA 檔案會移至隔離區。

當在端點上偵測到 PUA 時，macOS 上的 Microsoft Defender for Endpoint 會向使用者呈現通知，除非已停用通知。 威脅名稱會包含 "Application" 一詞。

## <a name="configure-pua-protection"></a>設定 PUA 保護

您可以透過下列其中一種方式，設定 macOS 的 Microsoft Defender for Endpoint 中的 PUA 保護：

- **Off**：已停用 PUA 保護。
- **Audit**： PUA files 會在產品記錄中報告，但不會在 Microsoft Defender Security Center 中報告。 使用者不會呈現任何通知，產品也不會採取任何動作。
- **封鎖**： PUA 檔案會在產品記錄和 Microsoft Defender Security Center 中報告。 使用者會看到一則通知，並由產品採取動作。

>[!WARNING]
>根據預設，會在 **審核** 模式中設定 PUA 保護。

您可以從命令列或從管理主控台，設定 PUA 檔案的處理方式。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>使用命令列工具來設定 PUA 保護：

在終端中執行下列命令，以設定 PUA 保護：

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>使用管理主控台來設定 PUA 保護：

在您的企業中，您可以從管理主控台（如 JAMF 或 Intune）設定 PUA 防護，類似于設定其他產品設定的方式。 如需詳細資訊，請參閱[macOS 主題上的 Microsoft Defender For Endpoint 的 Set 喜好設定](mac-preferences.md)中的[威脅類型設定](mac-preferences.md#threat-type-settings)一節。

## <a name="related-topics"></a>相關主題

- [在 macOS 上設定 Microsoft Defender for Endpoint 的喜好設定](mac-preferences.md)
