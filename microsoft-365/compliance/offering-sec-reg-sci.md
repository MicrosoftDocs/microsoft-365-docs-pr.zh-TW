---
title: 證券和 Exchange 傭金-法規系統合規性和完整性（SCI）
description: SCI 規則適用于 SCI 實體，包含這類自助組織（SROs）做為股票和選項交換、已註冊的清算機關和替代交易系統（ATSs）。
keywords: Microsoft 365, 合規性, 方案
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: e2b314934a51c16ab4e907b7d9f6208e7de21641
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065708"
---
# <a name="securities-and-exchange-commission-regulation-systems-compliance-and-integrity-sci"></a>證券和 Exchange 傭金：法規系統規範與完整性（SCI）

## <a name="about-regulation-sci"></a>關於法規 SCI

美國證券和 Exchange 傭金（SEC）是美國聯邦政府的獨立代理商，以及美國證券市場的主要 overseer 和調節器。 它會 wields 透過聯邦證券法律、提出新的證券規則，以及監督證券行業之市場法規的強制執行許可權。

在11月2014中，SEC 採用[法規系統合規性和完整性（SCI）](https://www.sec.gov/rules/final/2014/34-73639.pdf) （以及 SCI 報告 SCI 事件的表單），以加強美國證券市場的技術基礎結構。 此項管理法規的設計是為了降低系統停機頻率、在發生這類事件時提升恢復能力，並增加證券市場技術的 SEC 監督，並強制執行其規章。

SCI 規則適用于 SCI 實體，包含這類自助組織（SROs）做為股票和選項交換、已註冊的清算機關和替代交易系統（ATSs）。 規則主要規定直接支援主要證券市場功能的系統：貿易、淨空和結算、訂單路線、市場資料、市場規定和市場監控。

## <a name="microsoft-and-sec-regulation-sci"></a>Microsoft 和 SEC 法規 SCI

美國證券和 Exchange 傭金（SEC）採用規章 SCI，以加強運作及支援美國證券市場之金融組織的技術基礎結構。 根據 SEC 監管，其需求的設計是要確保這些系統具有高可用性、強恢復性和低延遲（低大量的郵件，但延遲較小）。

為了協助指導我們必須遵守這種法規的金融服務客戶，Microsoft 已發佈[Microsoft AZURE SEC 規章系統合規性和完整性雲端實施指南](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)。 本檔中的指導方針：

- 提供支援強恢復性、高可用性和低延遲的整體 Azure 功能的概述。
- 明確 Azure 位址的控制項區域和法規各部分。 Azure 功能和服務對 SCI 需求的這種點對點對應，會針對法規架構來測量 Azure 的規範。 它也可協助客戶瞭解他們可以將安全性責任移至 Azure，以在內部部署運作時，其已完全擁有。 這些功能是由 Microsoft 在 Azure Sla 中所做的承諾所支援。
- 指定客戶負責處理的每一項法規 SCI 需求，並提供 Azure 檔和服務，以協助他們處理這些責任。

本檔提供重要規章 SCI focus 區域的完整檢查清單。 這份檢查清單可協助金融組織瞭解如何採用 Azure 來協助確保他們的同盟、客戶和領導能夠遵守適用的法規需求。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure](https://aka.ms/AzureCompliance)

## <a name="how-to-implement"></a>實作方法

- [規章 SCI 實施指南](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)：對應 Azure 功能與法規的對應，並詳述法規遵從性的共用責任。
- [設計可靠的 Azure 應用程式](https://docs.microsoft.com/azure/architecture/resiliency/)：如何在 Azure 應用程式設計的每一個步驟中建立可靠性的簡短概述。
- [設計高可用性的應用程式](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs)：開發人員如何協助確保其 Azure 儲存應用程式具有高可用性。
- [風險評定與合規性指南](https://aka.ms/RiskGovernanceGuide)：建立 Microsoft 雲端服務風險評定的監管模型和調整通知。

## <a name="frequently-asked-questions"></a>常見問題集

**使用雲端技術時，共用責任是什麼意思？**

隨著計算環境從內部部署移至雲端的資料中心，安全性的責任也隨之，即雲端服務提供者（CSP）和客戶現在會分享該責任。 針對每個應用程式和解決方案，該責任中有多少是對客戶而言的，而 CSP 的多少取決於客戶部署的 Azure 模型（IaaS、SaaS 或 PaaS）。 客戶的責任是要瞭解他們對實施必要安全性控制的責任程度。 不過，Microsoft 提供指導方針來協助客戶導覽此複雜的動態。 如需詳細資訊，請參閱[Cloud 計算的共用責任](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91)。

**哪些金融機構可以利用 Azure 來協助滿足法規 SCI 需求？**

受此法規制約的財務組織或 SCI 實體可以部署 Azure。 SEC 說其法規適用于 ' 自助組織（SROs），包括股票和選項交換、已註冊的清算機關、FINRA、MSRB、替代貿易系統（ATSs）、貿易 NMS 和非 NMS 股票超過指定的容量閾值、整合的市場資料 disseminators （計畫處理器）和特定的免除清算機關。 '

## <a name="resources"></a>資源

- [每秒有關法規 SCI 的常見問題解答回應](https://www.sec.gov/divisions/marketreg/regulation-sci-faq.shtml)
- [商務持續性和嚴重損壞修復（BCDR）： Azure 配對區域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)
- [雲端計演算法規原則和 Microsoft Online Services 的合規性地圖](https://aka.ms/FinServ-Guide-US)
- [Microsoft 雲端財務服務合規性計劃](https://aka.ms/FSCP-Print)
- [Azure 的金融服務合規性](https://aka.ms/FinServ-Compliance-Azure)
- [Microsoft 金融服務](https://aka.ms/FinServ-Compliance)
- [Microsoft 和 SEC Rule 17a-4](offering-SEC-17a-4.md)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
