---
title: NIST SP 800-171
description: Microsoft 雲端服務遵循 NIST SP 800-171 指導方針，以保護 nonfederal 資訊系統中受控制的未分類資訊 (CUI) 。
keywords: Microsoft 365, 合規性, 方案
localization_priority: None
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9874a68978e5755e8e86ff476ec96170878a10da
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208085"
---
# <a name="nist-sp-800-171"></a>NIST SP 800-171

## <a name="about-nist-sp-800-171"></a>關於 NIST SP 800-171

美國國家標準和技術協會 (NIST) 會促進及維護度量標準和準則，以協助保護聯邦機構的資訊和資訊系統。 如需管理受控未分類資訊的管理順序 13556 (CUI) ，它已發佈 [NIST SP 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)， *保護 Nonfederal 資訊系統和組織中的受控未分類資訊*。 CUI 會定義為由政府 (或其代表的實體所建立的資訊（包括數位和實體）) ，但不保密，仍然機密且需要保護。

NIST SP 800-171 最初發佈于6月2015，已于此後更新數次，以回應演變的 cyberthreats。 它提供有關如何在 nonfederal 資訊系統和組織中安全地存取、傳送和儲存 CUI 的指導方針;其需求分為四個主要類別：

- 管理及保護的控制項和程式
- IT 系統的監控與管理
- 適用于使用者的清晰做法和程式
- 技術和實體安全性措施的實施

## <a name="microsoft-and-nist-sp-800-171"></a>Microsoft 和 NIST SP 800-171

已取得協力廠商評估組織，Kratos Secureinfo 和 Coalfire，與 Microsoft 合作以證明其範圍內的雲端服務符合 NIST SP 800-171 中的準則， *保護受控未分類資訊 (CUI) 在 Nonfederal 資訊系統和組織中*處理 CUI。 [Microsoft 對 FedRAMP](offering-fedramp.md)需求的實施，可協助確保 Microsoft 內部的雲端服務使用已到位的系統和做法，符合或超過 NIST SP 800-171 的需求。

NIST SP 800-171 的需求是 NIST SP 800-53 （FedRAMP 使用的標準）的子集。 NIST SP 800-171 的附錄 D 可將其 CUI 安全性需求直接對應至 NIST SP 800-53 中的相關安全性控制，其範圍內的雲端服務已在 FedRAMP 程式下評估並授權。

任何處理或儲存我們政府 CUI 的實體（調研機構、諮詢公司、製造承包商）都必須遵守 NIST SP 800-171 的嚴格需求。 這項證明意味著 Microsoft in 範圍的雲端服務可讓客戶在尋求部署 CUI 工作負載時，確保 Microsoft 符合完全規範。 例如，在其資訊系統中使用內部範圍的 Microsoft 雲端服務處理、儲存或傳輸「涵蓋的防禦資訊」的所有 DoD 承包商，都符合美國國防部 DFARS 子句，需要符合 NIST SP 800-171 的安全性需求。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure 政府](https://aka.ms/AzureCompliance)
- [美國政府的 Dynamics 365](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 美國政府社區雲端 (GCC) 、Office 365 GCC High 及 DoD](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>稽核、報告和認證

- [與 NIST SP 800-171 相容性的 Azure 政府證明](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a>實作方法

- [Azure 藍圖範例](https://docs.microsoft.com/azure/governance/blueprints/samples/)：取得支援以 NIST 為基礎的控制項的實施工作負載。

## <a name="frequently-asked-questions"></a>常見問題集

**我可以使用 Microsoft 對我的組織使用 NIST SP 800-171 的規範嗎？**

是。 Microsoft 客戶可以使用來自獨立協力廠商評估組織的報告中所述的審核控制項， (3PAO) FedRAMP 標準的一部分 FedRAMP 及 NIST 風險分析和資格工作。 這些報告證明 Microsoft 已在其範圍內雲端服務中實施之控制項的效能。 客戶負責確保其 CUI 工作負載符合 NIST SP 800-171 指導方針。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>使用 Microsoft 合規性管理員評估您的風險

[Microsoft 合規性管理員](compliance-manager.md) 是 [microsoft 365 規範中心](microsoft-365-compliance-center.md) 的一項功能，可協助您瞭解組織的合規性狀況，並採取行動以協助降低風險。 合規性管理員提供為此法規建立評估的高級範本。 在 [合規性管理員] 的 [ **評估範本** ] 頁面中尋找範本。 瞭解如何 [在合規性管理員中建立評估](compliance-manager-assessments.md)。

## <a name="resources"></a>資源

- [Microsoft DoD 認證符合 NIST 800-171 的需求](offering-DoD-DISA-L2-L4-L5.md)
- [NIST 800-171 合規性始于 Cybersecurity 檔](https://www.nist800171.com/)
- [Microsoft Cloud Services FedRAMP 授權](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [NIST 800-171 3.3 審計和責任與 Office 365 GCC 高](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [Microsoft 和 NIST Cybersecurity Framework](offering-nist-csf.md)
- [Microsoft 政府雲端](https://www.microsoft.com/enterprise/government)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
