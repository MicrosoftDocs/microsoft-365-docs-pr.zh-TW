---
title: 在 Microsoft Defender AV 中還原隔離的檔案
description: 您可以還原由 Microsoft Defender AV 隔離的檔案和資料夾。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3de9ddfc0cab12d2eea717c5d6b01e5b70b21213
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765788"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a>在 Microsoft Defender AV 中還原隔離的檔案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

如果 Microsoft Defender 防病毒已設定為偵測和修正裝置上的威脅，Microsoft Defender 防毒程式會隔離可疑檔案。 如果您確定隔離的檔案不是威脅，您可以將它還原。

1. 開啟 [ **Windows 安全性**]。
2. 選取 [ **病毒 & 威脅防護** ]，然後按一下 [ **保護歷程記錄**]。
3. 在所有近期專案的清單中，篩選 **隔離的專案**。
4. 選取您要保留的專案，並採取動作，例如 [還原]。

> [!TIP]
> 使用命令提示字元，也可以從隔離區還原檔案。 請參閱 [從隔離區還原](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)檔案。 

## <a name="related-articles"></a>相關文章

- [設定掃描的修正](configure-remediation-microsoft-defender-antivirus.md)
- [查看掃描結果](review-scan-results-microsoft-defender-antivirus.md)
- [根據檔案名、副檔名和資料夾位置，設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [設定及驗證由進程開啟之檔案的排除專案](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [設定 Windows Server 上的 Microsoft Defender 防病毒排除](configure-server-exclusions-microsoft-defender-antivirus.md)