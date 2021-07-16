---
title: Microsoft 365 隔離控制項
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 瞭解隔離控制在 Microsoft 365 內的運作方式，允許服務在必要的情況下運作或保持自治。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464074"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 隔離控制項 

Microsoft 持續運作，以確保多承租人架構的 Microsoft 365 支援企業級的安全性、機密性、隱私權、完整性、本機、國際和可用性[標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)。 由 Microsoft 提供的服務規模和範圍，使用大量的人工互動來管理 Microsoft 365，使其非常困難且非經濟。 Microsoft 365 服務是透過多個全域分散式資料中心提供，每個作業都具有極高的自動化，需要人工觸控或任何對客戶內容的存取。 我們的員工使用自動工具和高安全性的遠端存取，支援這些服務和資料中心。 

Microsoft 365 是由多種服務所組成，可提供重要的商務功能，並對整個 Microsoft 365 經驗產生貢獻。 每個服務都是自包含的，且設計為彼此整合。

Microsoft 365 是以下列原則為設計：

 - 以 **[服務為導向的架構](/previous-versions/aa480021(v=msdn.10))：** 以互通性服務的形式設計和開發軟體，以提供完善定義的商務功能。
 - **[運作安全性保證](https://www.microsoft.com/download/details.aspx?id=40872)：** 一種架構，包含透過 microsoft 獨有的各種功能所取得的知識，包括 Microsoft [安全性開發週期](https://www.microsoft.com/sdl/default.aspx)、 [microsoft 安全回應中心](https://technet.microsoft.com/library/dn440717.aspx)，以及 cybersecurity 威脅形勢的深入認知。

Microsoft 365 服務間相互運作，但會加以設計及實施，使其能獨立于自治服務進行部署及運作。 Microsoft segregates Microsoft 365 的責任和責任範圍，以降低未經授權或無意修改或誤用組織資產的機會。 Microsoft 365 小組已經定義角色，成為綜合角色存取控制機制的一部分。

## <a name="customer-content-isolation"></a>客戶內容隔離

租使用者中的所有客戶內容，都與其他承租人以及管理 Microsoft 365 所使用的作業和系統資料隔離。 在整個 Microsoft 365 中實施多種形式的保護，可將危及任何 Microsoft 365 服務或應用程式的風險降至最低。 多種保護表單也可防止未經授權的存取承租人或 Microsoft 365 系統本身的資訊。

如需 Microsoft 如何在 Microsoft 365 內對租使用者資料進行邏輯隔離的詳細資訊，請參閱[Microsoft 365 中的承租人隔離](microsoft-365-tenant-isolation-overview.md)。