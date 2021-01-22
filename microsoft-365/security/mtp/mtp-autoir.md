---
title: Microsoft 365 Defender 中的自動化調查與回應
description: 取得 Microsoft 365 Defender 中自動化調查與回應功能概觀 ，也稱為自我管理
keywords: 自動化、調查、警示、觸發、動作、補救、自我保護
search.appverid: met150
ms.prod: m365-security
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930327"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的自動化調查與回應

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。
>

## <a name="how-automated-investigation-and-self-healing-works"></a>自動調查與自我保護如何運作

當安全性警訊觸發時，您的安全性作業小組會決定要調查這些警示，並採取行動來保護貴組織。 優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。 安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。 Microsoft 365 Defender 中的自動調查及回應功能可協助進行自我調查。

請觀看以下影片，瞭解自助運作方式：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在 Microsoft 365 Defender 中，具有自助功能的自動化調查與回應可運作于您的裝置、電子郵件&內容和身分身分。
 
> [!TIP]
> 本文將說明自動化調查與回應如何運作。 若要設定這些功能，請參閱 [Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)中的設定自動化調查與回應功能。

## <a name="your-own-virtual-analyst"></a>您自己的虛擬分析師

想像您的第 1 層 / 第 2 層安全性作業小組中有一個虛擬分析員。 虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。 虛擬助理可以全天候工作、提供無限能力，以及接受大量調查和威脅補救。 如此一來，虛擬助理可以大幅減少回應時間，讓您的安全性作業小組能夠進行其他重要的策略專案。 如果這個案例聽起來是科幻作品，那不一樣！ 這樣的虛擬分析師是 Microsoft 365 Defender 套件的一部分，其名稱屬於 *自動化調查與回應。*

自動化調查與回應可讓安全性作業小組大幅提升貴組織處理安全性警訊和事件的能力。 使用自動化調查與回應，您可以降低處理調查與補救活動的成本，並完全利用您的威脅防護套件。 自動化調查及回應可協助您的安全性作業小組：

1. 判斷是否要針對威脅採取動作；
2. 執行 (或建議) 任何必要補救動作；
3. 判斷應該要進行哪些其他調查；以及
4. 針對其他警示重複採取必要程序。

## <a name="the-automated-investigation-process"></a>自動化調查程序

**警示** > **事件** > **自動化調查** > **結果** > **補救動作**

觸發的警示會建立事件，可開始自動化調查。 該調查會產生一或多個補救動作。 在 Microsoft 365 Defender 中，每個自動化調查會關聯 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Defender for Office 365 的訊號，如下表摘要： 

|實體 |威脅防護服務  |
|---------|---------|
|裝置 (也稱為端點)     |[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[適用於身分識別的 Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|電子郵件內容 (信箱中的檔案和郵件)     |[適用於 Office 365 的 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

每項調查都會針對 (*一* 項證據產生惡意、) 或沒有任何威脅。 視威脅類型與結果不同，補救動作會自動發生，或經過貴組織安全性作業小組的核准。 待處理和已完成的操作會列在[重要訊息中心](mtp-action-center.md)。

當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。 如果在其他地方看到受感染的實體，則自動化調查將擴大其範圍，以包括該實體，並且將執行一般安全性劇本。 

> [!NOTE]
> 並非每一個警示都會觸發自動化調查，而且並非每個調查都會觸發自動化修復動作;這完全取決於您組織的自動化調查與回應的安裝方式。 請參閱 [Microsoft 365 Defender 中的設定](mtp-configure-auto-investigation-response.md)自動化調查與回應功能。


## <a name="next-steps"></a>後續步驟

- [瞭解 Microsoft 365 Defender 中自動化調查及回應的先決條件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [為貴組織設定自動化調查與回應](mtp-configure-auto-investigation-response.md)
- [深入了解重要訊息中心](mtp-action-center.md)
