---
title: Microsoft 365 Defender 與 Azure Sentinel 的整合
description: 使用 Azure Sentinel 做為 Microsoft 365 Defender 事件及事件的 SIEM。
keywords: 事件、警示、調查、分析、回應、關聯、攻擊、電腦、裝置、使用者、身分識別、身分識別、信箱、電子郵件、365、microsoft、m365
search.product: eADQiWindows 10XVcnh
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
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: adb65c82713464da2df4d473d2fd7a055e0dbeb3
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415574"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Defender 與 Azure Sentinel 的整合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

azure sentinel 的 Microsoft 365 Defender connector (preview) 將所有 Microsoft 365 Defender 事件及警示資訊傳送至 Azure Sentinel，並保持事件同步。 

新增連接器之後，Microsoft 365 Defender 事件 &mdash; （包括所有相關聯的警示、實體及從 microsoft defender for Endpoint 接收的相關資訊）、microsoft defender for Identity、microsoft defender for Office 365 及 Microsoft Cloud App Security &mdash; 會以資料流程的)  (方式傳送至 azure sentinel，以執行與 azure sentinel 的會審和事件回應。 

在 azure Sentinel 中，事件仍保持雙向同步處理 Microsoft 365 Defender，可讓您利用 Azure 入口網站中 Microsoft 365 Defender 入口網站和 azure Sentinel 的優點，以進行事件調查和回應。

請留意 Azure Sentinel 整合與 Microsoft 365 Defender (4 分鐘) 的此簡短概述。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


以下說明運作方式。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defender 和 Azure Sentinel 之間的事件資料流程程與共享":::

## <a name="next-steps"></a>後續步驟

1. 深入瞭解[與 Azure Sentinel 的 Microsoft 365 Defender 整合](/azure/sentinel/microsoft-365-defender-sentinel-integration)。
2. [連線從 Microsoft 365 Defender 到 Azure Sentinel 的資料](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>另請參閱

- [Microsoft 365 Defender 中的事件概覽](incidents-overview.md)
- [使用 Azure Sentinel 調查事件](/azure/sentinel/tutorial-investigate-cases)
