---
title: 交易可接受的最小風險標準 (MARS-E) 2.0 架構
description: Microsoft 符合美國交易可接受的最小風險標準 (MARS-E)。
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
ms.openlocfilehash: ac5a027225ce0f7c4c719ba3a897f5bc6f5629d5
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065644"
---
# <a name="minimum-acceptable-risk-standards-for-exchanges-mars-e-20-framework"></a>交易可接受的最小風險標準 (MARS-E) 2.0 架構

## <a name="mars-e-20-framework-overview"></a>MARS-E 2.0 架構概觀

在 2012 年，美國聯邦醫療保險和補助服務中心 (CMS) 發佈了交易可接受的最小風險標準 (MARS-E)，該標準依據 CMS 資訊安全性和隱私權計劃。 文件套件 (包括指導方針、需求及範本) 旨在解決患者保護與平價醫療法案 (ACA) 及採用 ACA 的美國衛生及公共服務部法規要求。 國家標準暨技術研究院 (NIST) 特別刊物 800-53 作為上層架構，可針對 ACA 要求健康情況交換與市場之間的所有系統、介面和連線，建立安全性與合規性需求。

在 MARS-E 發行之後，NIST 發行了更新，特別刊物 800-53r4，以解決日益增加的線上安全性挑戰，包括應用程式安全性；測試人員和進階持續威脅；供應鏈風險；以及行動裝置與雲端計算的可信賴度、保證及復原能力。 CMS 接著修訂 MARS-E 架構，以與 NIST 800.53r4 中的更新控制項和參數保持一致，在 2015 年發行 MARS-E 2.0。

這些更新能解決受保護資料的健康情況交換機密性、完整性和可用性，其中包括個人識別資訊、受保護的健康資訊和聯邦稅務資訊。 MARS-E 2.0 架構是用來保護受保護的資料，並適用於所有 ACA 管理實體，包括交換或市場：聯邦、州、國家醫療補助或兒童健康保險計劃 (CHIP) 機關，以及支援承包商。

## <a name="microsoft-and-mars-e-20-framework"></a>Microsoft 和 MARS-E 2.0 架構

目前沒有適用於 MARS-E 的正式授權和資格鑑定程序。 不過，Microsoft Azure 平台服務已經歷「中等影響等級」的獨立 FedRAMP 稽核，以及「高等影響等級」的 Azure Government 稽核，並根據 FedRAMP 標準獲得授權。 雖然這些標準不會專門專注於 MARS-E，但是 MARS-E 控制項需求與目標緊密地保持一致，並致力於保護 Azure 上資料的機密性、完整性和可用性。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure 和 Azure Government](https://aka.ms/AzureCompliance)
- Intune

## <a name="audits-reports-and-certificates"></a>稽核、報告和認證

Microsoft 商務雲端服務每年會針對 FedRAMP 授權程序進行監視和評估。

## <a name="frequently-asked-questions"></a>常見問題集

**該標準適用於誰？**

MARS-E 適用於所有平價醫療法案管理實體，包括交換或市場，例如管理基本健康計劃的聯邦、州、醫療補助和 CHIP 機構，以及其所有承包商和轉包商。

**Microsoft 如何使用這個標準示範 Azure 和 Azure Government 合規性？**

使用第三方針對 FedRAMP 授權所準備的正式稽核報告，Microsoft 可以顯示相關控制項所述的資訊，這些報告示範 Azure 功能符合 MARS-E 安全性和隱私權控制項需求。 Microsoft 所實作的已稽核控制項，可保護儲存在 Azure 平台上資料的機密性、完整性和可用性，並對應至 MARS-E 中識別為Microsoft 責任的已定義適用法規需求。

**使用這個標準時，Microsoft 對維護合規性有何責任？**

Microsoft 可確保 Azure 平台符合管理[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)和適用服務等級協定 (SLA) 中定義的條款。 這些條款定義我們對於實作及維護足以保護 Azure 平台和監視系統控制項的職責。

**我是否可以為我的組織在 MARS-E 資格考核中使用 Microsoft 合規性？**

是。 FedRAMP 標準的第三方稽核報告證明 Microsoft 為了維護 Azure 平台安全性和隱私權而實作的控制項有效性。 Azure 和 Azure Government 客戶可以使用這些相關報告中所述的已稽核控制項作為自己 FedRAMP 和 MARS-E 風險分析和資格考核的一部分。

## <a name="resources"></a>資源

- MARS-E 法規指導方針，MARS-E 文件套件，2.0 版
    - [第 II 卷：交易可接受的最小風險標準](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/2-MARS-E-v2-0-Minimum-Acceptable-Risk-Standards-for-Exchanges-11102015.pdf)
    - [第 III 卷：適用於交換可接受的最小風險安全性與隱私權控制項的目錄](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/3-MARS-E-v2-0-Catalog-of-Security-and-Privacy-Controls-11102015.pdf)
- [線上服務的 Microsoft 合規性架構白皮書](https://aka.ms/compliance-framework)
- [Microsoft Online Services 條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
