---
title: Microsoft 365 Defender 的自動化調查和回應
description: 深入瞭解 Microsoft 365 Defender 中的自動化調查和回應功能（也稱為自我修復）
keywords: 自動化，調查，警示，觸發器，動作，修正，自我修復
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2b8872288291adc0b9fc5e1c1541f885711df230
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356700"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 的自動化調查和回應

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

> 想要體驗 Microsoft 365 Defender？ 您可以 [在實驗室環境中進行評估](https://aka.ms/mtp-trial-lab) ，或 [在實際執行中執行您的試驗專案](https://aka.ms/m365d-pilotplaybook)。
>

在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。 優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。 安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。 Microsoft 365 Defender 中的自動調查和回應功能（透過自我修復）可能會有所説明。

請觀看下列影片，瞭解自我修復的運作方式：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在 Microsoft 365 Defender 中，使用自我修復功能的自動化調查和回應可在您的裝置、電子郵件 & 內容和身分識別之間運作。 Microsoft 365 Defender 彙集了下列功能： 
- [Microsoft Defender for Endpoint 中的自動調查和修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Microsoft Defender for Office 365 中的自動調查和回應](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Azure 高級威脅偵測](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
本文說明自動化調查和回應的運作方式。 若要設定這些功能，請參閱 [在 Microsoft 365 Defender 中設定自動調查和回應功能](mtp-configure-auto-investigation-response.md)。

## <a name="your-virtual-analyst"></a>您的虛擬分析員

想像您的第 1 層 / 第 2 層安全性作業小組中有一個虛擬分析員。 虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。 虛擬助理可以全天候工作、提供無限能力，以及接受大量調查和威脅補救。 如此一來，虛擬助理可以大幅減少回應時間，讓您的安全性作業小組能夠進行其他重要的策略專案。 如果此案例好像是科學 fiction，就不是！ 這類虛擬分析員是 Microsoft 365 Defender 套件的一部分，而且其名稱是 *自動調查和回應*。

自動化調查和回應可讓您的安全性運作小組大幅增加組織的容量，以處理安全性警示和事件。 透過自動化調查和回應，您可以減少處理調查和修復活動的成本，並充分利用威脅防護套件。 自動化調查和回應可協助您進行安全性運作小組：

1. 判斷是否要針對威脅採取動作；
2. 執行 (或建議) 任何必要補救動作；
3. 判斷應該要進行哪些其他調查；以及
4. 針對其他警示重複採取必要程序。

## <a name="the-automated-investigation-process"></a>自動化調查程序

**警示** > **事件** > **自動化調查** > **結果** > **補救動作**

觸發的警示會建立事件，以開始自動調查。 該調查會產生一或多個補救動作。 在 Microsoft 365 Defender 中，每個自動調查都會針對所有 Microsoft Defender 身分識別、Microsoft Defender for Endpoint 和 Defender for Office 365 進行相互關聯的信號，如下表所示： 

|實體 |威脅防護服務  |
|---------|---------|
|裝置 (也稱為端點)     |[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[適用於身分識別的 Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|電子郵件內容 (信箱中的檔案和郵件)     |[適用於 Office 365 的 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

每一項調查都會產生 verdicts (*惡意*、 *可疑* 或 *沒有威脅*) 針對每個證據調查的部分。 根據威脅類型和產生的判定，您的組織的安全性運作小組會自動或核准執行修正動作。 待處理和已完成的操作會列在[重要訊息中心](mtp-action-center.md)。

當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。 如果在其他地方看到受感染的實體，則自動化調查將擴大其範圍，以包括該實體，並且將執行一般安全性劇本。 

> [!NOTE]
> 並非每個提醒都會觸發自動調查，而並非每項調查都會產生自動修復動作。這全都取決於組織如何設定自動調查和回應。 請參閱 [設定 Microsoft 365 Defender 中的自動化調查和回應功能](mtp-configure-auto-investigation-response.md)。


## <a name="next-steps"></a>後續步驟

- [請參閱 Microsoft 365 Defender 的自動化調查和回應必要條件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [為您的組織設定自動調查和回應](mtp-configure-auto-investigation-response.md)
- [深入了解重要訊息中心](mtp-action-center.md)
