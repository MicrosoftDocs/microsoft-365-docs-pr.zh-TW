---
title: Microsoft 365 Defender 中的自動化調查和回應
description: 深入瞭解 Microsoft 365 Defender 中的自動化調查和回應功能（也稱為自我修復）
keywords: 自動化，調查，警示，觸發器，動作，修正，自我修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 976a79be98efcbb5d7fd3749ddb0cdb282b1e3e3
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274565"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的自動化調查和回應

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

如果您的組織使用[Microsoft 365 Defender](microsoft-365-defender.md)，當偵測到惡意或可疑的活動或專案時，安全性作業小組會在 Microsoft 365 安全中心收到警示。 針對可能來自的威脅，在這種情況下，安全性小組通常會面臨解決大量提醒問題的難題。 幸運的是，Microsoft 365 Defender 包含自動調查和回應 (AIR) 能力，可協助安全性運作小組更有效率地處理威脅。

本文提供 AIR 的概述，並包含後續步驟和其他資源的連結。

> [!TIP]
> 想要體驗 Microsoft 365 Defender 嗎？ 您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。

## <a name="how-automated-investigation-and-self-healing-works"></a>自動化調查及自我修復的運作方式

在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。 優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。 安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。 在 Microsoft 365 Defender 中，利用自我修復的自動化調查和回應功能可能會有所説明。

請觀看下列影片，瞭解自我修復的運作方式： <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在 Microsoft 365 Defender 中，使用自我修復功能的自動化調查和回應可在您的裝置、電子郵件 & 內容和身分識別之間運作。
 
> [!TIP]
> 本文說明自動化調查和回應的運作方式。 若要設定這些功能，請參閱[設定 Microsoft 365 Defender 的自動化調查和回應功能](m365d-configure-auto-investigation-response.md)。

## <a name="your-own-virtual-analyst"></a>您自己的虛擬分析員

在第1層或第2層安全性作業小組中 Imagine 虛擬分析員。 虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。 虛擬分析員可以全天候運作，並可在大量進行調查和威脅修復時採取大量的功能。 這類虛擬分析員可大幅減少回應時間，以騰出安全性運作小組的其他重要威脅或戰略性專案。 如果此案例好像是科學 fiction，就不是！ 這類虛擬分析員是 Microsoft 365 Defender 套件的一部分，而且其名稱是 *自動調查和回應*。

自動化調查和回應功能可讓您的安全性運作小組大幅增加組織的容量，以處理安全性警示和事件。 透過自動化調查和回應，您可以減少處理調查和回應活動的成本，並充分利用威脅防護套件。 自動化調查和回應功能可協助您的安全性運作小組：

1. 決定威脅是否需要採取動作。
2. 採取 (或建議) 任何必要的修復動作。
3. 決定是否要進行其他調查。
4. 針對其他警示重複採取必要程序。

## <a name="the-automated-investigation-process"></a>自動化調查程序

警示會建立事件，可開始自動調查。 自動調查會產生每個證據的判定。 Verdicts 可以是：
- *惡意*
- *可疑* 
- *找不到威脅* 

識別惡意或可疑實體的修復動作。 修正動作範例包括：

- 將檔案傳送至隔離區
- 停止處理常式
- 隔離裝置
- 封鎖 URL 
- 其他動作

如需詳細資訊，請參閱[Microsoft 365 Defender 中的修復動作](m365d-remediation-actions.md)。

根據您的組織 [設定自動化調查和回應功能的方式](m365d-configure-auto-investigation-response.md) ，修復動作會自動採取或僅在安全操作小組核准時進行。 所有動作（不論是擱置或已完成的動作）都會列在 [重要訊息 [中心](m365d-action-center.md)]。

當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。 如果在其他地方看到受影響的實體，則自動調查會將其範圍擴大為包含該實體，而調查程式會重複。 

在 Microsoft 365 Defender 中，每個自動調查都會針對所有 microsoft defender 的身分識別、microsoft defender for Endpoint 和 microsoft defender （Office 365）進行關聯，如下表所匯總： 

|實體 |威脅防護服務  |
|:---------|:---------|
|裝置 (也稱為端點或機器)  |[端點的 Defender](../defender-endpoint/automated-investigations.md) |      
|內部部署 Active Directory 使用者、實體行為和活動     |[適用於身分識別的 Defender](/azure-advanced-threat-protection/what-is-atp) |      
|電子郵件內容 (可以包含檔案和 URLs 的電子郵件)      |[適用於 Office 365 的 Defender](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> 並非每個提醒都會觸發自動調查，而並非每項調查都會產生自動修復動作。 這取決於組織如何設定自動調查和回應。 請參閱 [設定自動調查和回應功能](m365d-configure-auto-investigation-response.md)。

## <a name="viewing-a-list-of-investigations"></a>查看調查清單

若要查看調查，請移至 [ **事件** ] 頁面。 選取事件，然後選取 [ **調查** ] 索引標籤。若要深入瞭解，請參閱 [自動調查的詳細資料和結果](m365d-autoir-results.md)。


## <a name="next-steps"></a>後續步驟

- [請參閱自動調查和回應的必要條件](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [為您的組織設定自動調查和回應](m365d-configure-auto-investigation-response.md)
- [深入了解重要訊息中心](m365d-action-center.md)
