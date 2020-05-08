---
title: 商品先期交易委員會（CFTC）規則1.31 （iso-c）美國
description: 獨立評估公司已驗證，Azure 和 Office 365 可協助財務公司符合 CFTC 規則1.31 記錄保留和不可變的儲存需求。
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
ms.openlocfilehash: 08f912492d1874b940156e3a6165f9476add7711
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065848"
---
# <a name="commodity-futures-trading-commission-cftc-rule-131c-d-united-states"></a>商品先期交易委員會（CFTC）規則1.31 （iso-c）美國

## <a name="about-cftc-rule-13c-d"></a>關於 CFTC 規則1.3 （3-d）

「[商品先期交易委員會](https://www.cftc.gov/)」（CFTC），是一種獨立美國聯邦 agency，會調節商品先期備貨和選項市場，以及最近的換購市場。  
  
長期 CFTC 規則1.31 會定義由 SEC Rule 17a-4 （f）建立的記錄保留需求。 此外，它會指定必須維護電子記錄五年，而且原始的兩年內保留「可隨時存取」，而且在整個保留期間內可供傭金或美國司法部門檢查。  
  
在2017中， [CFTC 修訂其規則](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrfederalregister/documents/file/2017-11014a.pdf)，修正並現代化其保留規定，以採用較少的規範性標準，可提供更多彈性以維護記錄的方式。 這使規則的技術不具特定，讓受管制實體可以選擇最適合其業務的技術，同時維持「保證保留過程的可靠性」的安全防護。 修改後的規則會從兩年內移除組織維護原始記錄的需求，但保留5年期的維護期間，這兩個公司的 harmonizes 做法是由 CFTC 和 SEC 管制。

## <a name="microsoft-and-cftc-rule-131c-d"></a>Microsoft 和 CFTC 規則1.31 （3-d）

金融服務客戶（如世界上最受管制的行業之一）受到複雜的置備，例如保留金融交易和相關通訊的非擦除和不可修改的狀態。 最具規範性的是美國商品先期備貨交易委員會（CFTC）的規則1.31，其可讓您選擇在電子化儲存介質上保留書和記錄，以 stipulates 對管制實體的嚴格需求。 儲存的記錄必須防篡改，但不能變更或刪除，直到指定的保留期間為止。 Microsoft Azure 永恆 Blob 儲存 with Policy Lock 和 Microsoft Office 365 （含保留鎖定）可協助金融機構符合 CFTC 規則1.31 （3-d）的儲存需求。

### <a name="microsoft-azure"></a>Microsoft Azure

若要評估 Azure 與 CFTC 規則1.31 （3-d）的相容性，Microsoft 保留了專門從事記錄管理和資訊管理、Cohasset 關聯的獨立評估事務所。 在產生的報告中， [CFTC 1.31 （c）–（d）合規性評估： Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)，Cohasset 使用原則鎖定選項驗證[Azure 不可變化的 blob 儲存區](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage)，以非擦除和不可讀寫（WORM）格式保留以時間為基礎的 blob，符合 CFTC 規則的原則要求。 每個 Blob （記錄）都會受到保護，無法進行修改、覆寫或刪除，直到必要的保留期間到期併發行任何關聯的合法保留期間為止。 具有敏感工作負載的軟體提供者和合作夥伴現在可以依靠 Azure 不可篡改的 Blob 存放區儲存為保留記錄的一個停止車間雲端方案。 金融機構現在可以組建自己的應用程式，利用這些功能，並保持不相容。

### <a name="microsoft-office-365"></a>Microsoft Office 365

若要評估 Office 365 與 CFTC 規則1.31 （3-d）的相容性，Microsoft 涉嫌從事主要獨立法律事務所，專門從事法規問題、Covington & Burling、LLP。 在產生的報告中，[在 Microsoft Office 365、資料保留和規則17A-4 規範](https://go.microsoft.com/fwlink/?linkid=830440)中進行封存，Covington 會驗證[具有保留鎖定的 Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy)包含封存功能，讓受管制的客戶能夠以一種方式來儲存資料，以協助滿足記錄保留的 CFTC 需求。

Office 365 中的封存可協助保留大量的資料，包括電子郵件、語音信箱、共用檔、立即訊息和協力廠商資料。 具體而言，Office 365 中的封存可讓客戶設定全域或細微的郵件保留原則，以儲存定義期間的資料，而不是以不可重寫、不可讀寫的格式使用。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure](https://aka.ms/AzureCompliance)
- [Office 365](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>稽核、報告和認證

[Azure & CFTC 規則 1.31-SEC 17a-4 （f） & CFTC 1.31 （c-d） Azure Storage 的合規性評估

[Office 365 & CFTC 規則 1.31-Office 365 中的封存、資料保留及 SEC 規則17a-4 法規遵從性

## <a name="how-to-implement"></a>實作方法

- [金融服務法規](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)：適用于雲端計算和 Microsoft online 服務之重要的 US 規章原則的符合性地圖。
- [風險評定與合規性指南](https://aka.ms/RiskGovernanceGuide)：建立 Microsoft 雲端服務風險評定的監管模型和調整通知。
- [金融使用案例](https://docs.microsoft.com/azure/industry/financial/)：使用案例概覽、課程及其他資源建立適用於金融服務的 Azure 解決方案。

## <a name="resources"></a>資源

- [Microsoft 金融服務合規性計劃](https://aka.ms/FSCP-Print)
- [Microsoft 商務用雲端服務與金融服務](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Azure 的金融服務合規性](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融服務雲端風險評定工具](https://aka.ms/FFIEC-CSDT)
- [Microsoft Office 365 保留原則](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融服務部落格](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
