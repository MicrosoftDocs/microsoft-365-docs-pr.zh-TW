---
title: 測試 Microsoft Defender for Endpoint 功能在稽核模式中的運作方式
description: 「稽核模式」可協助您瞭解在啟用裝置時，Microsoft Defender for Endpoint 如何保護您的裝置。
keywords: exploit guard，audit，audit，mode，enabled，disabled，test，demo，評估，實驗室
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059939"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>測試 Microsoft Defender for Endpoint 功能在稽核模式中的運作方式

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


您可以在稽核模式中啟用攻擊面降減規則、exploit protection、網路保護和受管理的資料夾存取。 「稽核模式」可讓您查看已啟用該功能時， *會* 發生什麼事的記錄。

在測試功能在組織中的運作方式時，您可能會想要啟用稽核模式。 這會協助確保您的企業營運應用程式不會受到影響。 您也可以瞭解在一段時間內，有多少可疑的檔修改嘗試次數。

功能不會封鎖或防止應用程式、腳本或檔案被修改。 不過，Windows 事件記錄會記錄事件，就好像已完全啟用這些功能。 透過「審計模式」，您可以查看事件記錄檔，以查看該功能在啟用時的影響。

若要尋找已審核的專案，請移至 **應用程式和服務**  >  **Microsoft**  >  **windows**  >  **windows Defender**  >  **運作**。

您可以使用 Defender for Endpoint 來取得每個事件的詳細資料，尤其是用於調查攻擊面降低規則。 使用 Defender for Endpoint 主控台，可在 [警示時程表和調查案例中調查問題](investigate-alerts.md)。

您可以使用「群組原則」、「PowerShell」和「設定服務提供者」 (Csp) 來啟用稽核模式。

> [!TIP]
> 您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Windows Defender Testground 網站，確認功能是否正常運作，並查看其運作方式。

 **審核選項** | **如何啟用稽核模式** | **如何查看事件**
|---------|---------|---------|
| 審核適用于所有事件 | [啟用受控資料夾存取權](enable-controlled-folders.md) | [受控資料夾存取事件](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| 審核適用于個別規則 | [啟用攻擊面減少規則](enable-attack-surface-reduction.md) | [攻擊面減少規則事件](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| 審核適用于所有事件 | [啟用網路保護](enable-network-protection.md) | [網路保護事件](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| 審核適用于個別的緩解 | [啟用 exploit protection](enable-exploit-protection.md) | [Exploit protection 事件](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>相關主題

* [保護裝置免受攻擊](exploit-protection.md)
* [使用攻擊面減少規則來減少攻擊面](attack-surface-reduction.md)
* [保護您的網路](network-protection.md)
* [保護重要的資料夾](controlled-folders.md)
