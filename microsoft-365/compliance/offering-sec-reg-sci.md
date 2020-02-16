---
title: 證券與 Exchange 委員會規定系統合規性和完整性 (SCI)
description: SCI 規則套用至 SCI 實體，其中包含此類 self-regulatory 組織 (SROs) 股票及選項交換、 註冊的清除行政機關，及替代方法貿易系統 (ATSs)。
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
ms.openlocfilehash: 4ad74c8d4ec71587f88a80c3ee109500e230be35
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071220"
---
# <a name="securities-and-exchange-commission-regulation-systems-compliance-and-integrity-sci"></a>證券與 Exchange 委員會： 規定系統合規性和完整性 (SCI)

## <a name="about-regulation-sci"></a>相關規定 SCI

美國證券和 Exchange 委員會 （秒） 是美國聯邦政府和主要領導人及調整的美國證券市場的獨立機構。 透過聯邦證券法律鑄造執法機構、 提出新的證券規則，以及監督的證券業的市場規定。

在 11 月 2014年秒採用[規定系統合規性和完整性 (SCI)](https://www.sec.gov/rules/final/2014/34-73639.pdf) （和報告 SCI 事件表單 SCI） 來增強在美國證券市場的技術基礎結構。 規定被為了減少系統中斷的頻率，改善恢復能力時這類事件發生，作業，並增加證券市場技術秒負責監督和強制執行的其規定。

SCI 規則套用至 SCI 實體，其中包含此類 self-regulatory 組織 (SROs) 股票及選項交換、 註冊的清除行政機關，及替代方法貿易系統 (ATSs)。 規則主要規範系統的直接支援金鑰證券市場函數： 貿易、 距離 settlement、 順序路由、 市場、 市場規定和資料市場鑰匙。

## <a name="microsoft-and-sec-regulation-sci"></a>Microsoft 和秒規定 SCI

美國證券和 Exchange 委員會 （秒） 採用規定 SCI 以加強操作和支援美國證券市場的財務組織的技術基礎結構。 下秒負責監督，其需求被為了確保這些系統具有高可用性、 強式恢復能力及低延遲 （大量的一點的延遲的郵件）。

若要協助美國金融服務部署客戶提供此規定必須遵守的指南，Microsoft 已發佈的[Microsoft Azure 秒規定系統合規性和完整性雲端實作指南](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)。 這份文件中的指南：

- 提供支援強式恢復能力、 高可用性和低延遲的整體 Azure 功能的概觀。
- 會清除哪些控制項區域和法規層面 Azure 的地址。 Azure 的功能和服務指派給 SCI 需求這點的點對應測量的法規架構的 Azure 規範。 它也有助於了解他們可以在此移動到其有完全擁有當他們 21vianet 運作的內部部署的 Azure 安全性責任的客戶。 這些功能是由 Microsoft 對於在 Azure Sla promise 所支援。
- 指定每個規定 SCI 需求，是地址，客戶的責任，並提供 Azure 文件和服務指派給協助他們位址這些責任。

本文件提供重要的規定 SCI 重點領域的完整檢查清單。 這份檢查清單可幫助了解如何他們可以採用以協助確保其管理者、 客戶和使用者可以遵守適用的法規需求的領導 Azure 的財務組織。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure](https://aka.ms/AzureCompliance)

## <a name="how-to-implement"></a>實作方式

- [規定 SCI 實作指南](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)： 對規定地圖 Azure 功能以及詳細資料合規性的共用的責任。
- [設計可靠的 Azure 應用程式](https://docs.microsoft.com/azure/architecture/resiliency/)： 如何將每個步驟的 Azure 應用程式的設計建置可靠性的簡要概觀。
- [設計高度可用的應用程式](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs)： 開發人員可以如何協助確保他們的 Azure 儲存體應用程式可用的高度。
- [風險評定與合規性指南](https://aka.ms/RiskGovernanceGuide)：建立 Microsoft 雲端服務風險評定的監管模型和調整通知。

## <a name="frequently-asked-questions"></a>常見問題集

**什麼共用責任平均數，當使用雲端技術？**

隨著運算從資料中心內部的環境移至雲端中，安全性的責任也會進入 — 的雲端服務提供者 (CSP) 及客戶現在共用該責任。 針對每一個應用程式和解決方案，該責任中有多少落在客戶及多少 CSP 取決於客戶部署 Azure 模型 — IaaS、 SaaS 或 PaaS。 它是以了解何種程度他們所負責實作所需的安全性控制客戶的責任。 不過，Microsoft 提供相關指導，以協助客戶瀏覽此複雜的動態。 如需詳細資訊，請閱讀[的雲端運算的共用責任](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91)。

**哪些金融機構可以利用 Azure 來幫助您滿足規定 SCI 需求？**

財務組織或受限於此規定的 SCI 實體可以部署 Azure。 秒指出其規定適用於 ' self-regulatory 組織 (SROs)，包括內建及選項交換註冊清除行政機關，FINRA 和 MSRB、 替代貿易貿易 NMS 和非 NMS 股票的系統 (ATSs) 超過指定磁碟區臨界值、 disseminators 的合併的市場資料 （計劃處理器） 和某些免除清除行政機關。 '

## <a name="resources"></a>資源

- [取得關於規定 SCI 的常見問題解答秒回應](https://www.sec.gov/divisions/marketreg/regulation-sci-faq.shtml)
- [商務持續性與災害復原 (BCDR): Azure 成對的區域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)
- [合規性的雲端運算法規的原則和 Microsoft Online Services 的分佈圖](https://aka.ms/FinServ-Guide-US)
- [Microsoft 雲端財務服務合規性計劃](https://aka.ms/FSCP-Print)
- [Azure 的金融服務合規性](https://aka.ms/FinServ-Compliance-Azure)
- [Microsoft 財務服務](https://aka.ms/FinServ-Compliance)
- [Microsoft 和 SEC Rule 17a-4](offering-SEC-17a-4.md)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下載方案背景資料

是否需要此方案的背景資料文件？ 下載 [PDF](https://download.microsoft.com/download/8/1/a/81aa04eb-3c1f-4c1a-ba7d-9d30032acc52/SEC_Reg_SCI-Compliance.pdf)。
