---
title: 聯邦風險與授權管理計畫 (FedRAMP)
description: Microsoft 授與 US 聯邦風險和授權管理計畫 P-ATOs 和 ATOs。
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
ms.openlocfilehash: 0ddb997246f2b7a23b25e1b611170c6163e1d670
ms.sourcegitcommit: b8a9994b26a6d9865212f5b1871286e719d1608e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43781473"
---
# <a name="federal-risk-and-authorization-management-program-fedramp"></a>聯邦風險與授權管理計畫 (FedRAMP)

## <a name="fedramp-overview"></a>FedRAMP 概述

美國聯邦風險和授權管理計畫（FedRAMP）是為了提供標準化的方法，以在聯邦資訊安全性管理法案（FISMA）下評估、監控和授權雲端計算產品和服務，並加速聯邦代理商採用安全的雲端解決方案。

「管理」和「預算」的 Office 現在需要所有的執行聯邦代理商使用 FedRAMP 來驗證雲端服務的安全性。 （其他代理商也採用它，所以也適用于公用部門的其他區域。）國家標準和技術協會（NIST） SP 800-53 會設定必要的標準、建立資訊系統的安全性類別（機密性、完整性和可用性），以評估組織的潛在影響是否應該危及其資訊和資訊系統。 FedRAMP 是證明雲端服務提供者（CSP）符合這些標準的程式。

向聯邦代理商銷售服務的 Csp desiring 可採用三個路徑，以示範 FedRAMP 合規性：

- 從共同授權委員會（JAB）取得臨時授權，以進行操作（P-ATO）。 JAB 是主要的控管和決策 FedRAMP。 來自國防部門的代表、Homeland 的安全性，以及一般的服務管理服務于董事會。 此局會授與 FedRAMP 規範的 Csp P-ATO。
- 接收從聯邦代理商運作的授權（ATO）。
- 或者，您可以個別合作，以開發符合程式需求的 CSP 提供套件。

這兩種路徑都需要由「FedRAMP 計畫管理 Office （PMO）」和由程式所獲得的獨立協力廠商組織進行評估的嚴格技術審查。

根據 NIST 指導方針，以三個影響層級授與 FedRAMP 授權：低、中和高。 這些層級會限制對組織的機密性、完整性或可用性喪失的影響：低（有限的影響）、中度（嚴重的不利影響）和高（嚴重或嚴重的影響）。

## <a name="microsoft-and-fedramp"></a>Microsoft 和 FedRAMP

Microsoft 的政府雲端服務（包括 Azure 政府、Dynamics 365 政府和 Office 365 美國政府）符合美國聯邦風險和授權管理計畫（FedRAMP）的苛刻需求，讓美國聯邦代理商能夠從 Microsoft 雲端的成本節約和嚴格安全性中受益。

Microsoft 政府雲端服務提供 public tool 客戶與 FedRAMP 及強大的指導方針和執行工具（包括[FedRAMP 高藍圖](https://aka.ms/fedrampblueprint)）相容，可協助客戶針對必須執行 FedRAMP 高控制措施的任何 Azure 部署架構，部署一組核心原則。

## <a name="microsoft-azure-p-atos"></a>Microsoft Azure P-ATOs

Azure 和 Azure 政府已從聯合授權板取得「高影響」層級的 P-ATO，其最大的 FedRAMP 資格鑒定，可授權 Azure 和 Azure 政府使用以處理高度機密的資料。

Azure 和 Azure 政府的 FedRAMP audit 包含的資訊安全性管理系統，涵蓋範圍內服務的基礎結構、開發、作業、管理及支援。 授與 P-ATO 後，CSP 仍然需要來自其使用之任何政府代理商的授權（ATO）。 針對 Azure，政府代理商可以使用其自己的安全性授權程式中的 Azure P-ATO，並依據它，作為發行同時符合 FedRAMP 需求的代理商 ATO 的基礎。

Azure 在 FedRAMP 高影響層級繼續支援較多的服務，而不是任何其他雲端提供者。 而且，Azure 公有雲端中 FedRAMP 高，可滿足許多美國政府客戶的需求，具有較嚴格需求的代理商會繼續依賴 Azure 政府，其可提供額外的保護措施，例如對人員的進一步篩選。 Microsoft 會列出目前在 Azure 政府中可用的所有[azure 公用服務](https://docs.microsoft.com/azure/azure-government/compliance/azure-services-in-fedramp-auditscope#azure-public-services-by-audit-scope)至 FedRAMP 高界限，以及為當年計畫的服務。

## <a name="microsoft-dynamics-365-us-government-ato"></a>Microsoft Dynamics 365 美國政府 ATO

Dynamics 365 美國政府已授與 ATO 機關和市內開發（HUD）的高影響層級的 FedRAMP 機關。 雖然憑證的範圍限制為政府系 Cloud，但 Dynamics 365 美國政府商務和企業方案卻是在相同組嚴格的 FedRAMP 控制項之後運作。

## <a name="microsoft-office-365-and-office-365-us-government-atos"></a>Microsoft Office 365 和 Office 365 美國政府 ATOs

- Office 365 和 Office 365 美國政府從美國衛生和人力服務（DHHS） ATO。
- Office 365 美國政府國防版已 P-ATO 美國國防資訊系統 Agency （DISA）。 任何想要部署 Office 365 美國政府國防版的客戶，都可能會使用 DISA P-ATO 產生代理商 ATO，以記錄其接受。
- Office 365 （enterprise and business 方案）和 Office 365 美國政府在 Inspector 的 DHHS Office 中，有 FedRAMP Agency ATO，其為中等影響層級。 Office 365 美國政府是第一個以雲端為基礎的電子郵件和共同作業服務，可取得這種授權。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure 和 Azure Government](https://go.microsoft.com/fwlink/p/?linkid=2095323)
- [美國政府的 Dynamics 365](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 和 Office 365 美國 Governmen](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- Office 365 美國政府國防版
- Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中
- Microsoft Defender ATP

> [!NOTE]
> Azure 政府中使用 Azure Active Directory 需要使用 azure public 雲端上部署于 Azure 政府以外的元件。

## <a name="audits-reports-and-certificates"></a>稽核、報告和憑證

Microsoft 必須每年重新認證其雲端服務，以維護其 P-ATO 和 ATO。 若要這麼做，Microsoft 必須不斷監控和評估其安全性控制，並示範服務的安全性仍保持合規性。

- [Microsoft cloud services FedRAMP 授權</span>](https://marketplace.fedramp.gov/#/product/azure-government?sort=productName&productNameSearch=azure)
- [Microsoft FedRAMP 稽核報告</span>](https://aka.ms/MicrosoftFedRAMPAuditDocuments)  

若要接收其他的 FedRAMP 報告，請傳送電子郵件至[Azure 聯邦檔](mailto:AzFedDoc@microsoft.com)。

## <a name="quickly-deploy-your-fedramp-solutions-on-azure-government"></a>在 Azure 政府上快速部署您的 FedRAMP 解決方案

讓 Microsoft 引導您完成 ATO 處理常式，並使用 FedRAMP 的高藍圖快速部署您的 FedRAMP 解決方案，這可協助客戶針對必須實施 FedRAMP 高控制措施的任何 Azure 部署架構，實施一組核心原則。

[開始使用 Azure FedRAMP 高藍圖](https://aka.ms/fedrampblueprint)

## <a name="frequently-asked-questions"></a>常見問題集

**Microsoft cloud services 是否遵從聯邦資訊安全性管理法案（FISMA）？**

FISMA 是一種聯邦法律，只需要我們的聯邦代理商和其合作夥伴才能從符合 FISMA 需求的組織購買資訊系統和服務。 大部分的代理商及其廠商會指出其是否符合 FISMA 規範，參考其如何在特殊出版物 800-53 rev 4 中符合 NIST 所識別的控制項。 FISMA 處理常式（但不是基礎標準本身）已由2011中的 FedRAMP 所取代。

**FedRAMP 適用的人員？**

' FedRAMP 對於聯邦代理商雲端部署和服務模型，「低」和「適中風險影響層級」是必要的。 ' 任何想要接洽 CSP 的聯邦代理商，都可能需要符合 FedRAMP 的規格。 此外，在聯邦政府使用的產品或服務中使用雲端技術的公司，可能需要取得 ATO。

**我的代理人會從何處開始執行其專屬的合規性工作？**

如需聯邦代理商順利流覽 FedRAMP 並符合其需求的相關步驟，請移至「[取得授權」：「代理程式授權](https://www.fedramp.gov/agency-authorization/)」。

**我是否可以在代理人的授權過程中使用 Microsoft 規範？**

是。 您可以使用 Microsoft 雲端服務的認證，作為需要聯邦政府機構 ATO 之任何計畫或倡議的基礎。 不過，您必須為這些服務之外的元件達成您自己的授權。

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>使用 Microsoft 合規性分數來評估風險

[Microsoft 合規性分數](compliance-score.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的預覽功能，可協助您了解組織的合規性狀況，並採取行動以協助降低風險。 [設定合規性分數](compliance-score-setup.md)後，請從**範本**下拉式功能表中選取預先設定的[FedRAMP 範本](https://go.microsoft.com/fwlink/?linkid=2118102)，以協助您的組織符合此法規的需求。

## <a name="resources"></a>資源

- [聯邦風險和授權管理計畫](https://www.fedramp.gov/)
- [FedRAMP 安全性評估架構](https://www.fedramp.gov/assets/resources/documents/FedRAMP_Security_Assessment_Framework.pdf)
- [在 Microsoft 中管理雲端的合規性](https://www.microsoft.com/trustcenter/common-controls-hub)
- [Microsoft 政府雲端](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Azure 規範服務](https://aka.ms/azurecompliance)
