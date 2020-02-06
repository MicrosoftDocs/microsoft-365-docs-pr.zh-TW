---
title: 雲端運算合規性控制目錄 (C5)
description: 了解 Azure、Azure Government 和 Azure Germany 如何展示符合雲端運算合規性控制目錄 (C5) 的證明。
keywords: Microsoft 365, 合規性, 方案
localization_priority: Priority
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
ms.openlocfilehash: 6b10147554bf1a742e0aa80bfaa072f5790cd327
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602660"
---
# <a name="cloud-computing-compliance-controls-catalog-c5"></a>雲端運算合規性控制目錄 (C5)

## <a name="c5-overview"></a>C5 概觀

在 2016 年，德國聯邦資訊安全局 (Bundesamt für Sicherheit in der Informationstechnik 或 BSI) 建立了雲端運算合規性控制目錄 (C5)。 C5 是稽核的標準，為雲端安全性以及德國政府機關和與政府合作的組織採公用雲端解決方案建立強制性的最低基準。 私人部門也日益採用 C5。

C5 需求目錄的目的旨在為認證雲端服務提供者提供一致的安全架構，並向客戶保證將對其資料進行安全管理。

C5 基於國際公認的 IT 安全標準，例如 ISO/IEC 27001:2013、Cloud Security Alliance Cloud Controls Matrix 3.0.1，以及 BSI 自己的 IT-Grundschutz 目錄。 此目錄包含跨 17 個網域的 114 個需求 (例如資訊安全性與實際安全性的組織)，其中包含所有雲端服務提供者的基本安全性需求，以及處理高度機密資料的額外需求和需要高可用性的情況。

BSI 也強調透明度。 在審核過程中，雲端提供者必須包含詳細的系統描述，並公開環境參數 (例如管轄權和資料處理位置、服務的佈建，以及其他發給雲端服務的認證)，以及雲端提供者對公共機構有公開義務的相關資訊。 這可協助潛在的雲端客戶決定雲端服務是否符合其基本需求，例如符合法律需求 (如資料保護、公司政策)，或能夠應付工業間諜的威脅。

## <a name="microsoft-and-c5"></a>Microsoft 和 C5

Microsoft 雲端服務針對 SOC 2 (AT 第 101 節) 標準，至少一年稽核一次。 根據 BSI，C5 稽核可與 SOC 2 稽核結合，以重複使用部分的系統描述和重疊控制的稽核結果。 Microsoft Azure、Azure Government 和 Azure Germany 根據獨立稽核員執行的稽核評估來維護合併的報告 (C5、SOC 2 類型 2、CSA STAR 證明)，該報告展示符合 C5 的證明。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure、Azure Government 和 Azure Germany](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- Office 365 德國

## <a name="audits-reports-and-certificates"></a>稽核、報告和憑證

- [Azure, Azure Government, and Azure Germany SOC 2 Type II Report.pdf](https://go.microsoft.com/fwlink/p/?linkid=2093520)

## <a name="frequently-asked-questions"></a>常見問題集

**我是否可以搭配使用 Microsoft 合規性與 C5 來協助組織取得自己的 C5 證明？**

是。 您可以使用 Microsoft 雲端服務的證明，做為需要 C5 的任何方案或計畫基礎。 不過，您需要為外部元件或在這些服務之上建置的元件實現您自己的 C5 證明。

**C5 與 IT-Grundschutz 目錄有何不同？**

IT-Grundschutz 提供了特定的方法，可協助組織識別及實施 IT 系統的安全性措施，也是建立 C5 標準的其中一個元素。 C5 為雲端服務提供者提供一組稽核標準，但會將實作的詳細資料留給雲端服務提供者。

**什麼是 Microsoft Cloud Germany？**

Microsoft Cloud Germany 實際位於德國，遵守德國隱私權法的要求，該要求限制了將個人資料傳輸到其他國家/地區的行為，並防範其他司法管轄機關存取可能違反國內法律的內容。 Azure Germany 從資料駐留在德國的德國資料中心提供 Azure 服務，並透過受德國法律管理的獨特資料信任者模型提供嚴格的資料存取和控制措施。

## <a name="resources"></a>資源

- 雲端運算合規性控制目錄 (C5) ([英文](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Controls_Catalogue/Compliance_Controls_Catalogue_node.html)) ([德文](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Anforderungskatalog/Anforderungskatalog_node.html))
- [使雲端運算合規性控制目錄 (C5) 參考國際標準](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/CloudComputing/ComplianceControlsCatalogue/Referencing_Cloud_Computing_Compliance_Controls_Catalogue.pdf;jsessionid=E5F009E49EB2689FAC3705578821BCB6.2_cid286?__blob=publicationFile&v=2)
- [雲端運算提供者的安全性建議](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/CloudComputing/SecurityRecommendationsCloudComputingProviders.pdf?__blob=publicationFile&v=2)
- [合規性報告：C5- und SOC-Testate Azure Deutschland](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=df100ae1-baf9-4785-8a6d-864c0bc5c308&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)
- Microsoft Azure Germany 的 [IT-Grundschutz 合規性活頁簿](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下載方案背景資料

是否需要此方案的背景資料文件？ 下載 [PDF](https://download.microsoft.com/download/E/F/6/EF619A4D-C17C-4279-8DC4-79C0620676AB/C5Germany-Compliance.pdf)。
