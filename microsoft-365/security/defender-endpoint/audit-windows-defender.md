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
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985093"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中測試攻擊面減少

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

在組織的安全性小組中，您可以設定攻擊面減少功能，以在稽核模式中執行，以查看他們的運作方式。 在 [稽核模式] 中，您可以啟用：

- 受攻擊面縮小規則
- 入侵防護
- 網路保護
- 和受管理的資料夾存取稽核模式

「稽核模式」可讓您查看已啟用該功能時， *會* 發生什麼事的記錄。

您可以在測試功能的運作方式時啟用稽核模式。 這會協助確保您的企業營運應用程式不會受到影響。 您也可以瞭解在一段時間內，有多少可疑的檔修改嘗試次數。

功能不會封鎖或防止應用程式、腳本或檔案被修改。 不過，Windows 事件記錄會將事件記錄為已完全啟用的功能。 透過「審計模式」，您可以查看事件記錄檔，以查看該功能在啟用後會有什麼影響。

若要尋找已審核的專案，請移至 **應用程式和服務**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **運作**。

使用 Defender for Endpoint 取得每個事件的詳細資料，尤其是用於調查攻擊面降低規則。 使用 Defender for Endpoint 主控台，可在 [警示時程表和調查案例中調查問題](investigate-alerts.md)。

您可以使用「群組原則」、「PowerShell」和「設定服務提供者」 (Csp) 來啟用稽核模式。

> [!TIP]
> 您也可以在[demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)流覽 Windows Defender 的 Testground 網站，確認功能是否正常運作，並查看其運作方式。

| 審核選項 | 如何啟用稽核模式 | 如何查看事件 |
|---------|---------|---------|
| 審核適用于所有事件 | [啟用受控資料夾存取權](enable-controlled-folders.md) | [受控資料夾存取事件](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| 審核適用于個別規則 | [啟用受攻擊面縮小規則](enable-attack-surface-reduction.md) | [攻擊面減少規則事件](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| 審核適用于所有事件 | [啟用網路保護](enable-network-protection.md) | [網路保護事件](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| 審核適用于個別的緩解 | [啟用入侵防護](enable-exploit-protection.md) | [Exploit protection 事件](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
