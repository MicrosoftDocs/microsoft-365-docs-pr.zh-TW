---
title: GDPR 的 Office 365 資訊保護概觀
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 取得 GDPR 的 Office 365 資訊保護概觀。了解如何探索、分類、保護及監視個人資料。
ms.openlocfilehash: 72ce55b5ceb2ec3ff95cada481ec4aee0bbe8eef
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197404"
---
# <a name="overview-of-office-365-information-protection-for-gdpr"></a>GDPR 的 Office 365 資訊保護概觀

這個解決方案示範如何保護 Office 365 服務中儲存的敏感資料。其包含探索、分類、保護及監控個人資料的規範性建議。這個解決方案會使用一般資料保護規定 (GDPR) 做為範例，但您可以套用相同的程序，以遵守許多其他法規。包含探索、分類、保護及監控個人資料的規範性建議。

GDPR 規定個人資料的收集、儲存、處理及共用。在 GDPR 下，個人資料廣泛地定義為與已識別或可識別之自然人 (即歐盟 (EU) 居民) 相關的任何資料。

文章 4 – 定義

> 「個人資料」表示與已識別或可識別之自然人 (資料主旨) 相關的任何資訊。可識別的自然人是可以直接或間接識別的人員，尤其藉由參照識別碼來識別，例如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身份的一個或多個因素；

這套解決方案旨在協助組織探索並保護 Office 365 中可能受到 GDPR 約束的個人資料。它不是作為 GDPR 規範認證提供的。組織有責任確保自己的 GDPR 規範，並建議諮詢其法律和規範團隊，或向專門從事規範工作的第三方尋求指導和建議。

[GDPR 評估](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D)是免費的快速線上自我評估工具，可協助您的組織檢閱其遵循 GDPR 的整體就緒程度。

## <a name="assess-and-manage-your-compliance-risk"></a>評估和管理您的規範風險

遵循 GDPR 規範的第一個步驟為評估 GDPR 是否適用於您的組織，如果適用，可到什麼程度。此分析包括了解您組織處理的資料，以及其所在位置。

### <a name="step-1--use-compliance-manager-to-view-the-regulation-requirements-and-track-your-progress"></a>步驟 1 — 使用合規性管理員來檢視規定需求及追蹤進度

合規性管理員可以協助您追蹤、實作及管理稽核控制措施，協助貴組織達到包括 GDPR 在內各種不同標準的規範。

![使用合規性管理員來檢視需求及追蹤進度](../media/Overview-image1.png)

如需詳細資訊，請參閱[合規性管理員](compliance-manager.md)。

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a>步驟 2 — 使用內容搜尋和敏感資訊類型來尋找個人資料 

探索環境中受到 GDPR 約束的個人資料。請使用內容搜尋與敏感資訊類型搭配，來：

- 尋找並報告個人資料所在的位置。

- 最佳化敏感資料類型和其他查詢，以尋找環境中的所有個人資料。

![使用內容搜尋和敏感資訊類型來尋找個人資料](../media/Overview-image2.png)

敏感資訊類型會定義自動化程序如何辨識特定資訊類型，例如健康服務號碼和信用卡號碼。本文包含一組可以用作起點的資訊類型。即將對歐盟國家中的個人資料推出許多更敏感性資訊類型。

如需詳細資訊，請參閱[搜尋並找出個人資料](search-for-and-find-personal-data.md)。 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a>分類、保護及監視 Office 365 和其他 SaaS 應用程式中的個人資料

Office 365 中用於資訊保護的部分功能也可以用來保護其他 SaaS 應用程式中的敏感資料。

![分類、保護及監視個人資料](../media/Overview-image3.png)

本節的其餘部分 (步驟 3 - 5) 描述此圖。

### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a>步驟 3 — 決定除了敏感資訊類型外，是否還要使用標籤

敏感資訊類型是一種分類形式。請參閱[設計個人資料的分類結構描述架構](architect-a-classification-schema-for-personal-data.md)，以決定是否也要實作標籤。若要套用標籤，請參閱[將標籤套用至 Office 365 中的個人資料](apply-labels-to-personal-data-in-office-365.md)。

在圖例中，敏感資訊類型和標籤適用於整個 Office 365。不久以來，您可以使用這些項目與雲端 App 安全性搭配，來尋找其他 SaaS 應用程式 (例如 Box 和 Salesforce) 中的敏感資料。

### <a name="step-4--protect-personal-data-in-office-365"></a>步驟 4 — 保護 Office 365 中的個人資料 

保護個人資料從 Office 365 資料外洩防護開始。有數個針對保護個人資料存取而建議的其他功能，包括電子郵件的 Office 365 郵件加密。

這些保護能以特定資料集為目標：

- 網站和文件庫層級權限

- 網站層級外部共用原則

- 網站層級裝置存取控制

保護 Office 365 和其他雲端服務的存取包括：

- 企業行動力 + 安全性 (EMS) 的身分識別與裝置存取保護

- 特許存取管理

- Windows 10 安全性功能

如需套用保護的詳細資訊，請參閱[將保護套用至 Office 365 中的個人資料](apply-protection-to-personal-data-in-office-365.md)。

### <a name="step-5--monitor-for-leaks-of-personal-data"></a>步驟 5 — 監視個人資料的外洩

Office 365 資料外洩防護報告可提供監視敏感資料的最詳細層級。您可以設定自動警示，並使用稽核記錄調查洩露。雲端 App 安全性可將尋找並監視敏感性資料的功能擴充至其他 SaaS 提供者。如需這些工具的詳細資訊，請參閱[監視個人資料的洩露](/security/office-365-security/monitor-for-leaks-of-personal-data.md)。
