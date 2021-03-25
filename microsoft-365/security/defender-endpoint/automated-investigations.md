---
title: 使用自動調查以調查和修正威脅
description: 瞭解 Microsoft Defender for Endpoint 中的自動調查流程。
keywords: 自動化、調查、偵測、defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: d2effb44c145a4fbf1006446685dbcd703754e6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166206"
---
# <a name="overview-of-automated-investigations"></a>自動化調查的概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


想要瞭解其運作方式？ 觀賞下列影片： <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

自動調查中的技術會使用各種檢查演算法，並以安全分析員所使用的程式為基礎。 AIR 功能的設計目的是要檢查提醒並立即採取行動以解決違規行為。 AIR 功能大幅減少警示數量，讓安全性運作能夠將重點放在更複雜的威脅及其他高價值的計畫上。 在重要訊息 [中心](auto-investigation-action-center.md)追蹤所有修正動作（不論是擱置或已完成的動作）。 在「行動中心」中，待定的動作會獲核准 (或拒絕) ，而且必要時可復原完成的動作。

本文提供 AIR 的概述，並包含後續步驟和其他資源的連結。

> [!TIP]
> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)。

## <a name="how-the-automated-investigation-starts"></a>自動化調查的開始方式

在觸發警示時，或在安全性操作員開始調查時，就可以開始進行自動調查。

|情況  |會發生什麼事  |
|---------|---------|
|觸發警示     | 一般來說，當觸發 [警示](review-alerts.md) 時，會自動進行調查，而且會建立 [事件](view-incidents-queue.md) 。 例如，假設某個惡意檔案位於裝置上。 偵測到該檔案時，會觸發警示，並建立事件。 在裝置上開始自動調查過程。 因為其他的警示是由於其他裝置上的相同檔案而產生，所以它們會新增至相關聯的事件及自動調查。         |
|手動開始調查     | 您的安全性運作小組可以手動啟動自動調查。 例如，假設安全性操作員正在複查裝置清單，並注意到裝置具有高風險層級。 安全操作員可在清單中選取要開啟其快顯視窗的裝置，然後選取 [ **啟動自動調查**]。 |

## <a name="how-an-automated-investigation-expands-its-scope"></a>自動化調查如何擴充其範圍

在執行調查時，系統會將從裝置產生的任何其他警示新增至進行中的自動調查，直到完成調查為止。 此外，如果在其他裝置上看到相同威脅，就會將這些裝置新增至調查。

如果在另一個裝置中看到 incriminated 實體，自動化調查程式會將其範圍擴大至包含該裝置，並在該裝置上開始一般的安全性行動手冊。 如果在此擴充程式從相同實體找到10個以上的裝置，則該展開動作需要核准，而且會顯示在 [擱置的 **動作** ] 索引標籤上。

## <a name="how-threats-are-remediated"></a>如何修正威脅

在觸發警示時，自動調查執行時，會針對每個證據調查產生一個判定。 Verdicts 可以是 
- *惡意*;
- *可疑*;或 
- *找不到威脅*。 

當達到 verdicts 時，自動調查可能會產生一或多項修復動作。 修正動作的範例包括將檔案傳送至隔離區、停止服務、移除排程的任務等等。 若要深入瞭解，請參閱 [修復動作](manage-auto-investigation.md#remediation-actions)。  

根據您組織的 [自動化設定層級](automation-levels.md) 以及其他安全性設定，修正動作可以自動進行，也可以只在安全操作小組核准時進行。 其他可影響自動修復的安全性設定包括 [保護可能有害的應用程式](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA) 。 

在重要訊息 [中心](auto-investigation-action-center.md)追蹤所有修正動作（不論是擱置或已完成的動作）。 如有必要，您的安全性作業小組可以復原修正動作。 若要深入瞭解，請參閱 [在自動調查後複查和核准修正動作](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)。

> [!TIP]
> 請參閱 Microsoft 365 security center 中新的整合調查頁面。 若要深入瞭解，請參閱 [ (NEW！ ) 整合調查] 頁面](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)。


## <a name="requirements-for-air"></a>空氣需求

您的組織必須具有 Defender for Endpoint (請參閱 [Microsoft defender For endpoint) 的基本需求](minimum-requirements.md) 。

目前，AIR 只支援下列作業系統版本：
- Windows Server 2019
- Windows 10，版本 1709 (OS 組建16299.1085，含 [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 或更新版本
- Windows 10，版本 1803 (OS 組建17134.704，含 [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 或更新版本
- Windows 10，版本 [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) 或更新版本

## <a name="next-steps"></a>後續步驟

- [深入瞭解自動化層級](automation-levels.md)
- [請參閱互動式指南：使用 Microsoft Defender for Endpoint 調查和修正威脅](https://aka.ms/MDATP-IR-Interactive-Guide)
- [在 Microsoft Defender for Endpoint 中設定自動調查和修正功能](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>另請參閱

- [PUA 保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Microsoft Defender for Office 365 中的自動調查和回應](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-air)
- [Microsoft 365 Defender 的自動化調查和回應](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
