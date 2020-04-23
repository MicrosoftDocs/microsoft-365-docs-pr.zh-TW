---
title: NIST SP 800 –171
description: Microsoft 雲端服務遵循 NIST SP 800 –171的指導方針，以保護 nonfederal 資訊系統中控制的未分類資訊（CUI）。
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
ms.openlocfilehash: e1bd69e7038ce3bf6372a3f53cd985ce54f350a8
ms.sourcegitcommit: b8a9994b26a6d9865212f5b1871286e719d1608e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43781448"
---
# <a name="nist-sp-800171"></a>NIST SP 800 –171

## <a name="about-nist-sp-800171"></a>關於 NIST SP 800 –171

美國國家標準和技術協會（NIST）推廣及維護度量標準和準則，以協助保護聯邦機構的資訊和資訊系統。 如需管理受控未分類資訊（CUI）的管理順序13556，已發佈[NIST SP 800 – 171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)，*以保護 Nonfederal 資訊系統和組織中的可控未分類資訊*。 CUI 會定義為政府（或代表其代表的實體）所建立的資訊，但不保密，其仍機密且需要保護。

NIST SP 800 –171最初是在2015年6月發佈，並已經過多次更新，以回應演變 cyberthreats。 它提供有關如何在 nonfederal 資訊系統和組織中安全地存取、傳送和儲存 CUI 的指導方針;其需求分為四個主要類別：

- 管理及保護的控制項和程式
- IT 系統的監控與管理
- 適用于使用者的清晰做法和程式
- 技術和實體安全性措施的實施

## <a name="microsoft-and-nist-sp-800171"></a>Microsoft 和 NIST SP 800 –171

已取得協力廠商評估組織，Kratos Secureinfo 和 Coalfire，與 Microsoft 合作以證明其範圍內的雲端服務符合 NIST SP 800 –171中的準則，在*Nonfederal 資訊系統和組織中，保護受控未分類資訊（CUI）*，在處理 CUI 時。 [Microsoft 對 FedRAMP](offering-fedramp.md)需求的實施可協助確保 Microsoft 內建的雲端服務使用已到位的系統和做法，符合或超過 NIST SP 800 –171的需求。

NIST SP 800 –171的需求是 NIST SP 800-53 的子集（FedRAMP 使用的標準）。 在 NIST SP 800 –171中的附錄 D，可將其 CUI 安全性需求的直接對應至 NIST SP 800-53 中的相關安全性控制，但範圍內的雲端服務已在 FedRAMP 程式下評估並授權。

任何處理或儲存 US 政府 CUI 的實體（調研機構、諮詢公司、製造承包商）都必須遵守 NIST SP 800 –171的嚴格需求。 這項證明意味著 Microsoft in 範圍的雲端服務可讓客戶在尋求部署 CUI 工作負載時，確保 Microsoft 符合完全規範。 例如，在其資訊系統中，使用範圍內的 Microsoft 雲端服務處理、儲存或傳輸「涵蓋的防禦資訊」的所有 DoD 承包商，都符合美國國防 DFARS 子句，需要符合 NIST SP 800 –171的安全性需求。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure 政府](https://aka.ms/AzureCompliance)
- [美國政府的 Dynamics 365](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 美國政府社區雲端（GCC）、Office 365 GCC High 及 DoD](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>稽核、報告和憑證

- [具有 NIST SP 800 –171的 Azure 政府規範證明](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a>實作方法

- [Azure 藍圖範例](https://docs.microsoft.com/azure/governance/blueprints/samples/)：取得支援以 NIST 為基礎的控制項的實施工作負載。

## <a name="frequently-asked-questions"></a>常見問題集

**我可以使用 Microsoft 法規遵從性，針對我的組織使用 NIST SP 800 –171？**

是。 Microsoft 客戶可以使用來自獨立協力廠商評估組織（3PAO）的報告中所述的已審核控制項，其 FedRAMP 標準是其自有 FedRAMP 和 NIST 風險分析和資格努力的一部分。 這些報告證明 Microsoft 已在其範圍內雲端服務中實施之控制項的效能。 客戶負責確保其 CUI 工作負載符合 NIST SP 800 –171的指導方針。

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>使用 Microsoft 合規性分數來評估風險

[Microsoft 合規性分數](compliance-score.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的預覽功能，可協助您了解組織的合規性狀況，並採取行動以協助降低風險。 [設定合規性分數](compliance-score-setup.md)後，請從**範本**下拉式功能表中選取預先設定的[NIST 800-171 範本](https://go.microsoft.com/fwlink/?linkid=2117526)，以協助您的組織符合此法規的需求。

## <a name="resources"></a>資源

- [Microsoft DoD 認證符合 NIST 800 –171的需求](offering-DoD-DISA-L2-L4-L5.md)
- [NIST 800 –171相容性始于 Cybersecurity 檔](https://www.nist800171.com/)
- [Microsoft Cloud Services FedRAMP 授權](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [NIST 800-171 3.3 審計和責任與 Office 365 GCC 高](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [Microsoft 和 NIST Cybersecurity Framework](offering-nist-csf.md)
- [Microsoft 政府雲端](https://www.microsoft.com/enterprise/government)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下載方案背景資料

是否需要此方案的背景資料文件？ 下載 [PDF](https://download.microsoft.com/download/9/8/F/98F1D966-FB62-4B58-B6F0-8F3DCCAC484A/NIST_SP-800-171-Compliance.pdf )。
