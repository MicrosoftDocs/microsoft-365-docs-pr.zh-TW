---
title: Microsoft 365 隔離控制
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 15805c2fb57cbcaa33c5ba24dcbcaa378feea4bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688589"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 隔離控制 

Microsoft 連續運作，以確保 Microsoft 365 的多承租人架構支援企業層級的安全性、機密性、隱私權、完整性、本機、國際和可用性 [標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)。 由 Microsoft 提供的服務規模和範圍，可讓您在使用重要人工互動功能的情況中管理 Microsoft 365，使其非常困難，非經濟。 Microsoft 365 服務是透過多個全域分散式資料中心提供，每個都具有許多要求人工觸控或任何對客戶內容的作業。 我們的員工使用自動工具和高安全性的遠端存取，支援這些服務和資料中心。 

Microsoft 365 是由多種服務所組成，可提供重要的商務功能，並可促進整個 Microsoft 365 的體驗。 每個服務都是自包含的，且設計為彼此整合。

Microsoft 365 的設計原則如下：

 - 以**[服務為導向的架構](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10))：** 以互通性服務的形式設計和開發軟體，以提供完善定義的商務功能。
 - **[運作安全性保證](https://www.microsoft.com/download/details.aspx?id=40872)：** 一種架構，包含透過 microsoft 獨有的各種功能所取得的知識，包括 Microsoft [安全性開發週期](https://www.microsoft.com/sdl/default.aspx)、 [microsoft 安全回應中心](https://technet.microsoft.com/library/dn440717.aspx)，以及 cybersecurity 威脅形勢的深入認知。

Microsoft 365 服務間相互運作，但會加以設計及實施，使其能獨立于自治服務進行部署及運作。 Microsoft segregates Microsoft 365 的責任和責任範圍，以減少未授權或無意修改或誤用組織資產的機會。 Microsoft 365 小組已定義角色，成為綜合角色存取控制機制的一部分。

## <a name="customer-content-isolation"></a>客戶內容隔離

租使用者中的所有客戶內容，都與其他承租人和 Microsoft 365 管理中所使用的作業和系統資料隔離。 您可以在整個 Microsoft 365 中實施多種保護形式，以最大限度降低任何 Microsoft 365 服務或應用程式的威脅。 多種保護表單也可防止未經授權的存取承租人或 Microsoft 365 系統本身的資訊。

如需 Microsoft 如何在 Microsoft 365 內實現租使用者資料邏輯隔離的詳細資訊，請參閱 [microsoft 365 中的承租人隔離](microsoft-365-tenant-isolation-overview.md)。
