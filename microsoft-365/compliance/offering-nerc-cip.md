---
title: 北美電力可靠性公司 (NERC)
description: Azure 和 Azure Government 適用於受 NERC CIP 標準規範在雲端中部署特定工作負載的註冊實體。
keywords: Microsoft 365, 合規性, 方案
localization_priority: Priority
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
ms.openlocfilehash: f4394a66242a981ab179b07f45e82132f68968d7
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305353"
---
# <a name="north-american-electric-reliability-corporation-nerc"></a>北美電力可靠性公司 (NERC)

## <a name="about-the-nerc"></a>關於 NERC

[北美電力可靠性公司](https://www.nerc.com/) (NERC) 是非營利組織法規授權單位，使命為確保北美大量電力系統的可靠性。 NERC 受美國聯邦能源管理委員會 (FERC) 和加拿大政府機構的監督。 在 2006 年，FERC 依照 2005 年《能源政策法案》(美國公共法 109-58)，向 NERC 授與電力可靠性組織 (ERO) 的職銜。 NERC 開發和強制執行稱為 NERC [重要基礎結構保護 (CIP) 標準](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)的可靠性標準。

## <a name="microsoft-and-the-nerc-cip-standard"></a>Microsoft 和 NERC CIP 標準

北美電力可靠性公司 (NERC) 是非營利組織法規授權單位，使命為確保北美大量電力系統的可靠性。 NERC 受美國聯邦能源管理委員會 (FERC) 和加拿大政府機構的監督。 在 2006 年，FERC 依照 2005 年《能源政策法案》(美國公共法 109-58)，向 NERC 授與電力可靠性組織 (ERO) 的職銜。 NERC 開發和強制執行稱為 NERC [重要基礎結構保護 (CIP) 標準](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)的可靠性標準。

所有大量電力系統擁有者、操作員和使用者必須[遵守 NERC CIP 標準](https://www.nerc.com/pa/comp/Pages/default.aspx)。 這些實體向 NERC 註冊。 雲端服務提供者和協力廠商不受 NERC CIP 標準約束；不過 CIP 標準包含[註冊實體](https://www.nerc.com/pa/comp/Pages/Registration.aspx)在大量電力系統 (BES) 運行中使用廠商時應考慮的目標。 運行大量電力系統的 Microsoft 客戶對確保自己遵守 NERC CIP 標準負有全部責任。 無論 Microsoft Azure 或 Microsoft Azure Government 都不構成 BES 或 BES 網路資產。

如 NERC 在當前的 [CIP 標準](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf)和 NERC [詞彙表](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)中所述，BES 網路資產會執行監視或控制 BES 的即時功能，並且會在受損後 15 分鐘內影響 BES 的可靠運作。 為了在雲端運算中適當容納 BES 網路資產和受保護的網路資產，[需要修訂](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx) NERC CIP 標準中的現有定義。 但是，有許多工作負載處理 CIP 敏感性資料，並且不受 15 分鐘規則限制，包括 BES 網路系統資訊 (BCSI) 的廣泛類別。

Azure 和 Azure Government 適用於受 NERC CIP 標準 (包括 BCSI 工作負載) 規範部署特定工作負載的註冊實體。 Microsoft 向有興趣在 Azure 或 Azure Government 中遵守 NERC CIP 合規性義務部署資料和工作負載的註冊實體提供以下文件：

- [NERC CIP 標準和雲端運算](https://aka.ms/AzureNERC)是一份技術白皮書，該技術白皮書基於適用於雲端服務提供者 (例如FedRAMP) 的既有第三方稽核，討論了 NERC CIP 需求的合規性考量。 它涵蓋了雲端操作人事的背景檢測，並回答有關註冊實體感興趣的邏輯隔離和多租用戶的常見問題。 其中也解決了內部部署與雲端部署之間的安全性考量。
- [NERC 稽核的雲端實作指南](https://aka.ms/AzureNERCGuide)是一份指導文件，提供當前 NERC CIP 標準需求集與構成 FedRAMP 基礎的 [NIST SP 800-53 Rev 4](https://nvd.nist.gov/800-53/Rev4) 控制集之間的控制項對應。 它被設計為技術指導方針，以協助註冊實體解決針對在雲端部署之資產的 NERC CIP 合規性要求。 該文件包含預先填入的[可靠性標準稽核工作表 (RSAWs)](https://www.nerc.com/pa/comp/Pages/Reliability-Standard-Audit-Worksheets-\(RSAWs\).aspx)敘述，協助解釋 Azure 控制如何解決 NERC CIP 需求，以及針對註冊實體如何使用 Azure 服務實作自有控制項的指導。

NERC ERO 企業[發佈](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx)合規性監視與執行計畫 (CMEP) 的[做法指南](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf)，為 ERO 企業的 CMEP 人員提供指導方針，評定已註冊實體對指定 BCSI 儲存位置以及註冊實體實作之任何存取控制的存取授權程序。 此外，NERC 檢閱的 Azure 控制實作詳細資料，以及與 NERC CIP-004-6 和 CIP-011-2 標準相關的 FedRAMP 稽核證據，都適用於 BCSI。 根據 ERO 發放的做法指南和已檢閱的 FedRAMP 控制項來確保註冊實體加密其資料，註冊實體在雲端部署 BCSI 和關聯的工作負載不需要額外的指導方針或說明。 但是，註冊實體最終要根據自己的事實和情況負責遵守 NERC CIP 標準。 註冊實體需要檢閱 [NERC 稽核的雲端實作指南](https://aka.ms/AzureNERCGuide)，以協助記錄其程序和用於授權對 BCSI 儲存位置進行電子存取的證據，包括 Azure 和 Azure Government 中用於 BCSI 加密的加密金鑰管理。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure 和 Azure Government](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>稽核、報告和憑證

Microsoft 必須每年重新認證其雲端服務，以維護其 P-ATO 和 ATO。 若要這麼做，Microsoft 必須持續監控和評估其安全性控制，並表明其維持合規性。

- [Microsoft 雲端服務授權](https://marketplace.fedramp.gov/?sort=productName&productNameSearch=azure#/product/azure-government)
- [Microsoft FedRAMP 稽核報告](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="how-to-implement"></a>實作方法

### <a name="nerc-cip-standards-and-cloud-computing"></a>NERC CIP 標準和雲端運算

解決考量為工作負載採用雲端解決註冊實體的合規性，受 NERC CIP 標準規範。

[深入了解](https://aka.ms/AzureNERC)

### <a name="cloud-implementation-guide-for-nerc-audits"></a>NERC 稽核的雲端實作指南

技術指導方針可協助註冊實體進行對 Azure 或 Azure Government 中部署之資產的 NERC 稽核。 

[深入了解](https://aka.ms/AzureNERCGuide)

## <a name="frequently-asked-questions"></a>常見問題集

**誰負責遵守 NERC CIP 標準？**

所有大量電力系統擁有者、操作員和使用者必須[遵守 NERC CIP 標準](https://www.nerc.com/pa/comp/Pages/default.aspx)。 這些實體向 NERC 註冊。 雲端服務提供者和協力廠商不受 NERC CIP 標準約束；不過 CIP 標準包含[註冊實體](https://www.nerc.com/pa/comp/Pages/Registration.aspx)在大量電力系統 (BES) 運行中使用廠商時應考慮的目標。 運行大量電力系統的 Microsoft 客戶對確保自己遵守 NERC CIP 標準負有全部責任。 無論 Azure 或 Azure Government 都不構成 BES 或 BES 網路資產。

若要評估 Azure 和 Azure Government 對受 NERC CIP 標準規範的資料和工作負載的適用性，註冊實體應諮詢其自身的法令遵循長和 NERC 稽核員。 他們需要檢閱 [NERC 稽核的雲端實作指南](https://aka.ms/AzureNERCGuide)，以協助記錄其程序和雲端部署資產的證據。

**哪些工作負載可以讓註冊實體部署在 Azure 和 Azure Government 上？**

NERC [CIP 標準](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf)和[詞彙表](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)指出 BES 網路資產會執行監視獲控制 BES 的即時功能，並且會在受損後 15 分鐘內影響 BES 的可靠運作。 為了在雲端運算中適當容納 BES 網路資產和受保護的網路資產，[需要修訂](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx) NERC CIP 標準中的現有定義。 但是，有許多工作負載處理 CIP 敏感性資料，並且不受 15 分鐘規則限制，包括 BES 網路系統資訊 (BCSI) 的廣泛類別。

NERC ERO 企業[發佈](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx)合規性監視與執行計畫 (CMEP) 的[做法指南](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf)，為 ERO 企業的 CMEP 人員提供指導方針，評定已註冊實體對指定 BCSI 儲存位置以及註冊實體實作之任何存取控制的存取授權程序。 此外，NERC 檢閱的 Azure 控制實作詳細資料，以及與 NERC CIP-004-6 和 CIP-011-2 標準相關的 FedRAMP 稽核證據，都適用於 BCSI。 根據 ERO 發放的做法指南和已檢閱的 FedRAMP 控制項來確保註冊實體加密其資料，註冊實體在雲端部署 BCSI 和關聯的工作負載不需要額外的指導方針或說明。 但是，註冊實體最終要根據自己的事實和情況負責遵守 NERC CIP 標準。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>使用 Microsoft 合規性管理員來評定風險

[Microsoft 合規性管理員](compliance-manager.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的功能，可協助您了解組織的合規性態勢，並採取行動以協助降低風險。 合規性管理員會提供特優範本以為此法規建立評定。 可在合規性管理員的 [評定範本]**** 頁面尋找範本。 了解如何[在合規性管理員中建立評定](compliance-manager-assessments.md)。

## <a name="resources"></a>資源

- [NERC 合規性指導](https://www.nerc.com/pa/comp/guidance/)
- [NERC 網路安全性 - 供應鏈風險管理](https://www.nerc.com/pa/Stand/Pages/CIP0131RI.aspx)
- [NERC 合規性和強制性](https://www.nerc.com/pa/comp/Pages/default.aspx)
- [NERC 組織和認證](https://www.nerc.com/pa/comp/Pages/Registration.aspx)
- [Microsoft 和 FedRAMP](offering-fedramp.md)
- Microsoft 和 CSA STAR [證明](offering-csa-star-attestation.md)與[認證](offering-csa-star-certification.md)
- [Microsoft 和 SOC 2 報告](offering-soc.md)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
