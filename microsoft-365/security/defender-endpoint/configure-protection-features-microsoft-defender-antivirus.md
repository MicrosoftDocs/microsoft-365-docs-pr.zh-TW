---
title: 啟用和設定 Microsoft Defender 防毒軟體保護功能
description: 在 Microsoft Defender AV 中啟用行為型、啟發式和即時保護。
keywords: 啟發式、機器學習、行為監控、即時保護、always on、Microsoft Defender 防毒軟體、反惡意程式碼、安全性、Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925552"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>設定行為、啟發學習法和即時保護


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防毒軟體會使用數種方法來提供威脅防護：

- 雲端提供的保護，用於近乎立即偵測和封鎖新的和新興的威脅
- Always on 掃描，使用檔案及程式列為監控和其他試探法 (也稱為「即時保護」 ) 
- 以機器學習、人力和自動化資料分析及深入的威脅抵禦研究為基礎的專屬保護更新

您可以設定 Microsoft Defender 防毒軟體如何使用這些方法與群組原則，System Center 設定管理、PowerShell Cmdlet，以及 Windows 管理工具 (WMI) 。

本節包含設定進行永不間斷掃描的功能，包括如何偵測並封鎖視為不安全的應用程式，但可能偵測為惡意程式碼。

如需如何啟用及設定 Microsoft Defender 防毒軟體雲端提供的保護，請參閱[使用下一代 Microsoft Defender 防毒軟體技術進行雲端傳送的保護](cloud-protection-microsoft-defender-antivirus.md)。

## <a name="in-this-section"></a>本節內容

 主題 | 描述
---|---
[偵測並封鎖潛在的垃圾應用程式](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | 偵測並封鎖您網路中可能不需要的應用程式，例如廣告軟體、瀏覽器修飾符和工具列，以及惡意或虛假的防病毒應用程式
[啟用和設定 Microsoft Defender 防毒軟體保護功能](configure-real-time-protection-microsoft-defender-antivirus.md) | 啟用和設定即時保護、啟發及其他永不 Microsoft Defender 防毒軟體的監控功能
