---
title: Microsoft 365 中的資料復原
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
description: 在本文中，我們將深入瞭解 Microsoft 365 中的資料恢復功能和復原的設計和原則。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2474417100c68139c53d71e6031bbbe13b994677
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331881"
---
# <a name="data-resiliency-in-microsoft-365"></a>Microsoft 365 中的資料復原

考慮到雲端計算的複雜性質，Microsoft 很注意，如果發生問題，則不是這樣。 我們設計雲端服務，以最大化可靠性，並在發生錯誤時將負面影響降至最低。 我們已超越信賴複雜實體基礎結構的傳統策略，而且我們已直接在雲端服務中建立冗余。 我們採用複雜的實體基礎結構和更多智慧軟體的組合，將資料恢復到我們的服務中，並為我們的客戶提供高可用性。 

## <a name="resiliency-and-recoverability-are-built-in"></a>恢復功能和可恢復性是內建 

以恢復性和復原的方式開始，假設基礎基礎結構和程式在某些情況下會失敗：硬體 (基礎結構) 會失敗、人工會犯錯誤，軟體也會有錯誤。 雖然軟體發展人員不會考慮到雲端之前未考慮到這些事項，但在典型的 IT 實施中處理這些問題的方式，在雲端之前是非常不同的：

- 首先，硬體和基礎結構保護非常重要。 這意味著具有99.99% 可靠性的資料中心需要大量的電源和網路冗余，而且伺服器是以硬體型集群、雙電源、雙網路介面，以及類似的方式來執行。 
- 其次，處理常式是極其重要的。 運作小組維護嚴格的程式、對 windows 的變更所採用的工作，而且經常會產生大量的專案管理工作負載。 
- 第三，部署是以 glacial 節奏進行。 部署不含來源的程式碼表示要等候修補程式版本，主要版本版本則涉及硬體取代和大量的資本 outlay。 此外，修正問題的唯一方法是回復。 因此，大部分的 IT 組織只會部署主要版本，以避免工作保持最新狀態。 
- 最後，已部署系統的規模，以及其 interconnectedness 的層級，都比現在更小。 

目前，客戶預期來自 Microsoft 的連續創新，但不會降低品質，這是 Microsoft 的服務和軟體以恢復性和恢復為基礎而建立的原因之一。 

## <a name="microsoft-365-data-resiliency-principles"></a>Microsoft 365 資料恢復原則

恢復性指的是雲端架構服務可經受某些類型的失敗的能力，但在客戶的觀點上仍然能完全運作。 資料恢復意味著不論 Microsoft 365 中發生的失敗為何，重要的客戶資料會保持不變且不會受到影響。 為做到這一點，Microsoft 365 服務的設計是圍繞五個特定的恢復原則：

- 有重要且非重要的資料。 非重要資料 (例如，郵件是否已讀取) 可以在少見的失敗案例中刪除。 重要資料 (例如，客戶資料) （例如電子郵件訊息）應以極高的成本加以保護。 在設計目標中，傳遞的郵件訊息永遠很重要，也就是郵件已讀取的情況不重要。 
- 客戶資料的複本必須分割成不同的容錯區域，或盡可能多的容錯網域 (例如，資料中心可透過單一認證進行存取 (程式、伺服器或操作員) # A3，以提供失敗隔離。 
- 必須監視重要的客戶資料，以失敗任何原子性、一致性、隔離性、耐用性 (ACID) 部分。 
- 客戶資料必須受到保護，避免損毀。 必須主動掃描或監視、修復和恢復。 
- 客戶動作中大部分的資料遺失結果，讓客戶可以使用 GUI 自行進行復原，讓他們能夠還原意外刪除的專案。 
 
透過將我們的雲端服務組建至這些原則，並結合可靠的測試和驗證，Microsoft 365 可以符合和超過客戶的需求，同時可確保平臺的持續創新和改進。 

## <a name="related-links"></a>相關連結

- [處理資料損毀](microsoft-365-dealing-with-data-corruption.md)
- [惡意程式碼與勒索軟體防護](microsoft-365-malware-and-ransomware-protection.md)
- [監視及自我修復](microsoft-365-monitoring-and-self-healing.md)
- [Exchange 資料恢復功能](microsoft-365-exchange-data-resiliency.md)
