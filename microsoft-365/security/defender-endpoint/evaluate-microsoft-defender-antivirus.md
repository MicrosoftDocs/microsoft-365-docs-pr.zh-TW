---
title: 評估 Microsoft Defender 防毒軟體
description: 所有規模的企業都可以使用本指南評估及測試 Windows 10 中 Microsoft Defender 防毒軟體所提供的保護。
keywords: Microsoft Defender 防毒軟體，cloud protection，cloud，反惡意程式碼，安全性，Defender，評估，測試，保護，比較，即時保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c558a7799bff61a0ee80db31ee476ad611053c0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926616"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>評估 Microsoft Defender 防毒軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

使用此指南可判斷 Microsoft Defender 防毒軟體如何防止病毒、惡意程式碼和潛在的有害應用程式。

>[!TIP]
>您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範網站，以確認下列功能正在運作中，並查看其運作方式：
>- 雲端提供的保護
>- Fast 教學 (包括第一次看到區塊) 
>- 可能有害的應用程式封鎖

它說明適用于小型和大型企業的 Microsoft Defender 防毒軟體的下一代保護功能，以及它們如何增加整個網路的惡意程式碼偵測和保護。

您可以選擇個別設定和評估每個設定，或一次全部設定。 我們已根據一般評估案例分組類似設定，並包含使用 PowerShell 來啟用設定的指示。

您可以使用 PDF 格式，以供離線查看使用的指南：

- [下載 PDF 格式的指南](https://www.microsoft.com/download/details.aspx?id=54795)

您也可以下載可讓指南中所述之所有設定自動啟用的 PowerShell。 您可以在上述的 PDF 下載上，或從 PowerShell 圖庫中個別取得腳本：

- [下載 PowerShell 腳本，以自動設定設定](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> 此指南目前適用于 Microsoft Defender 防毒軟體的單一機器評估。 啟用本指南中的所有設定可能不適合實際部署。
>
> 如需實際部署及透過網路監視 Microsoft Defender 防毒軟體的最新建議，請參閱[Deploy Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)。

## <a name="related-topics"></a>相關主題

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
- [部署 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)