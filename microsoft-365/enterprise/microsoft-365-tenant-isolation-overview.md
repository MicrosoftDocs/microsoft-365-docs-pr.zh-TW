---
title: Microsoft 365 中的租使用者隔離
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
description: 本文摘要說明 Microsoft 如何在雲端服務（如 Microsoft 365）中強制執行租使用者隔離。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b52d936bb00ac0adef0baf428cbc5f9a8f8aba49
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194646"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Microsoft 365 中的租使用者隔離

雲端計算的其中一個主要優點是，許多客戶都有共同共同使用的共同基礎結構，進而可實現規模經濟效益。 這個概念稱為 *多重* 租用。 Microsoft 可以持續運作，以確保雲端服務的多承租人架構支援企業層級的安全性、機密性、隱私權、完整性及可用性標準。

根據從「 [可信計算](https://www.microsoft.com/trust-center) 」和「 [安全性開發生命週期](https://www.microsoft.com/securityengineering/sdl/)」收集的重大投資和經驗，設計 Microsoft 雲端服務是為了避免所有租使用者可能會惡意處理其他租使用者，並已實施安全性措施，以避免一個承租人的動作影響其他租使用者的安全性或服務，或存取另一個租使用者的內容。

在多租使用者環境中維護租使用者隔離的兩個主要目標如下：

1.    防止對承租人的客戶內容洩露或未經授權存取和
2.    防止一個承租人的動作對其他租使用者的服務造成不良影響

在整個 Microsoft 365 中已實施多種保護形式，以防止客戶損妥 Microsoft 365 服務或應用程式或未經授權存取其他承租人或 Microsoft 365 系統本身的資訊，包括：

- 在每個承租人中 Microsoft 365 服務的邏輯隔離，都是透過 Azure Active Directory 授權和以角色為基礎的存取控制來達成。
- SharePoint線上提供儲存層級的資料隔離機制。
- Microsoft 使用嚴謹的實體安全性、背景篩選和多層次的加密策略，以保護客戶內容的機密性和完整性。 所有的 Microsoft 365 資料中心都具有生物統計學存取控制，大多數需要使用 palm 列印才能獲得實體存取權。 此外，所有以美國為基礎的 Microsoft 員工都必須在聘用過程中成功完成標準背景檢查。 如需 Microsoft 365 中用於管理存取之控制項的詳細資訊，請參閱[Microsoft 365 系統管理存取控制](/compliance/assurance/assurance-administrative-access-controls-overview)。
- Microsoft 365 使用的服務端技術會在靜止和傳輸中加密客戶內容，包括 BitLocker、每個檔案加密、傳輸層安全性 (TLS) 和網際網路通訊協定安全性 (IPsec) 。 如需 Microsoft 365 中加密的特定詳細資料，請參閱[Microsoft 365 中的資料加密技術](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)。

以上所列的保護功能提供了可靠的邏輯隔離控制，可提供與獨立實體隔離所提供之威脅防護和緩解同等的威脅。

## <a name="related-links"></a>相關連結

- [Azure Active Directory 中的隔離與存取控制](microsoft-365-isolation-in-azure-active-directory.md)
- [Office Graph 與 Delve 中的租用戶隔離](microsoft-365-isolation-in-graph-and-delve.md)
- [Microsoft 365 搜尋中的租用戶隔離](microsoft-365-isolation-in-microsoft-365-search.md)
- [資源限制](/compliance/assurance/assurance-resource-limits)
- [監視及測試租用戶界限](/compliance/assurance/assurance-monitoring-and-testing)
- [Microsoft 365 中的隔離與存取控制](microsoft-365-isolation-in-microsoft-365.md)