---
title: Microsoft 365 中的租使用者隔離
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
description: 本文摘要說明 Microsoft 如何在雲端服務（如 Microsoft 365）中強制執行租使用者隔離。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea97cbe9b6c23f7ed0006fbe78a4deb5f35b5ab7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688637"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Microsoft 365 中的租使用者隔離

雲端計算的其中一個主要優點是，許多客戶都有共同共同使用的共同基礎結構，進而可實現規模經濟效益。 這個概念稱為 *多重*租用。 Microsoft 可以持續運作，以確保雲端服務的多承租人架構支援企業層級的安全性、機密性、隱私權、完整性及可用性標準。

根據從「 [可信計算](https://www.microsoft.com/trust-center) 」和「 [安全性開發生命週期](https://www.microsoft.com/securityengineering/sdl/)」收集的重大投資和經驗，設計 Microsoft 雲端服務是為了避免所有租使用者可能會惡意處理其他租使用者，並已實施安全性措施，以避免一個承租人的動作影響其他租使用者的安全性或服務，或存取另一個租使用者的內容。

在多租使用者環境中維護租使用者隔離的兩個主要目標如下：

1.    防止對承租人的客戶內容洩露或未經授權存取和
2.    防止一個承租人的動作對其他租使用者的服務造成不良影響

已在整個 Microsoft 365 中實施多種保護形式，以防止客戶損除 Microsoft 365 服務或應用程式，或未經授權存取其他承租人或 Microsoft 365 系統本身的資訊，包括：

- Microsoft 365 服務各租使用者中的客戶內容邏輯隔離，是透過 Azure Active Directory 授權和以角色為基礎的存取控制來實現。
- SharePoint 線上在儲存層級提供資料隔離機制。
- Microsoft 使用嚴謹的實體安全性、背景篩選和多層次的加密策略，以保護客戶內容的機密性和完整性。 所有 Microsoft 365 資料中心都具有生物識別存取控制，大多數需要 palm 列印才能獲得實體存取權。 此外，所有以美國為基礎的 Microsoft 員工都必須在聘用過程中成功完成標準背景檢查。 如需 Microsoft 365 中用於管理存取之控制項的詳細資訊，請參閱 [microsoft 365 管理存取控制](microsoft-365-administrative-access-controls-overview.md)。
- Microsoft 365 使用服務端技術，在靜止和傳輸中加密客戶內容，包括 BitLocker、每個檔案加密、傳輸層安全性 (TLS) 和網際網路通訊協定安全性 (IPsec) 。 如需 Microsoft 365 中加密的特定詳細資料，請參閱 [microsoft 365 中的資料加密技術](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview)。

以上所列的保護功能提供了可靠的邏輯隔離控制，可提供與獨立實體隔離所提供之威脅防護和緩解同等的威脅。

## <a name="related-links"></a>相關連結

- [Azure Active Directory 中的隔離與存取控制](microsoft-365-isolation-in-azure-active-directory.md)
- [Office Graph 與 Delve 中的租用戶隔離](microsoft-365-isolation-in-graph-and-delve.md)
- [Microsoft 365 搜尋中的租用戶隔離](microsoft-365-isolation-in-microsoft-365-search.md)
- [Office 365 影片中的租用戶隔離](microsoft-365-isolation-in-microsoft-365-video.md)
- [資源限制](microsoft-365-resource-limits.md)
- [監視及測試租用戶界限](microsoft-365-monitoring-and-testing.md)
- [Microsoft 365 中的隔離與存取控制](microsoft-365-isolation-in-microsoft-365.md)
