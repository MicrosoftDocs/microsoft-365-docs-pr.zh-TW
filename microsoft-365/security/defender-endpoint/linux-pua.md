---
title: 在 Linux 上使用 Microsoft Defender for Endpoint 偵測並封鎖可能有害的應用程式
description: 在 Linux 上使用 Microsoft Defender for Endpoint (PUA) 偵測並封鎖可能有害的應用程式。
keywords: microsoft、defender、atp、linux、pua、pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9631fc2eb1cb791f48f107482474d1bb8e2fd62b
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903855"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上使用 Microsoft Defender for Endpoint 偵測並封鎖可能有害的應用程式

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

在 PUA 中的 Defender for 中，可能有害的應用程式 () 保護功能可偵測並封鎖您網路中端點上的 PUA 檔案。

這些應用程式不會被視為病毒、惡意程式碼或其他類型的威脅，但是可能會對對其效能或使用不良影響的端點執行動作。 PUA 也可以參考被視為具有不良信譽的應用程式。

這些應用程式可能會增加網路受到惡意程式碼感染的風險，使惡意程式碼感染難以識別，而且可以在清理應用程式時浪費 IT 資源。

## <a name="how-it-works"></a>運作方式

適用于 Linux 的 Defender for Linux 可以偵測並報告 PUA 檔案。 當以封鎖模式設定時，PUA 檔案會移至隔離區。

當在端點上偵測到 PUA 時，Linux 的 Defender Endpoint 會在威脅歷程記錄中保存感染記錄。 您可以從 Microsoft Defender 安全性中心入口網站或透過 `mdatp` 命令列工具來進行記錄。 威脅名稱會包含 "Application" 一詞。

## <a name="configure-pua-protection"></a>設定 PUA 保護

您可以採用下列其中一種方式，設定 PUA 的 Defender for Linux 中的保護：

- **Off**：已停用 PUA 保護。
- **Audit**： PUA files 會在產品記錄中報告，但不會在 Microsoft Defender Security Center 中報告。 不會將感染記錄儲存在威脅史中，也不會對產品採取任何動作。
- **封鎖**： PUA 檔案會在產品記錄和 Microsoft Defender Security Center 中報告。 感染的記錄會儲存在威脅史中，且會在產品採取動作。

>[!WARNING]
>根據預設，會在 **審核** 模式中設定 PUA 保護。

您可以從命令列或從管理主控台，設定 PUA 檔案的處理方式。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>使用命令列工具來設定 PUA 保護：

在終端中執行下列命令，以設定 PUA 保護：

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>使用管理主控台來設定 PUA 保護：

在您的企業中，您可以從管理主控台（如 Puppet 或 Ansible）設定 PUA 防護，類似于設定其他產品設定的方式。 如需詳細資訊，請參閱為 Linux 文章的[Defender 的設定偏好設定](linux-preferences.md)的 [[威脅類型](linux-preferences.md#threat-type-settings)設定] 區段。

## <a name="related-articles"></a>相關文章

- [為 Linux 設定 Defender for Endpoint 的喜好設定](linux-preferences.md)
