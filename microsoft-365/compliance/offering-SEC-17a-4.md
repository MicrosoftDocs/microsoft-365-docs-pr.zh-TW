---
title: 證券和 Exchange 傭金（SEC）原則17a-4 （f）美國
description: 獨立評估公司已驗證，Azure 和 Office 365 可協助財務公司符合 SEC Rule 17a-4 （f）記錄保留和不可變的儲存需求。
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
ms.openlocfilehash: 63a7c4f7385ec3d782ff030374ba344406c6d094
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126662"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>證券和 Exchange 傭金（SEC）原則17a-4 （f）美國

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft 和 SEC Rule 17a-4 （f）

[美國證券和 Exchange 傭金（SEC）](https://www.sec.gov/)是美國聯邦政府的獨立代理商，以及美國證券市場的主要 overseer 和調節器。 它會 wields 透過聯邦證券法律、提出新的證券規則，以及監督證券行業之市場法規的強制執行許可權。

每秒為管制實體定義嚴格和明確的需求，以選擇在電子化儲存介質上保留書籍和記錄。 它建立了[17 cfr 240.17 a-3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3)和[17 cfr 240.17 a-4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64) ，以控制證券經紀人的保留期間（包括保留期間）。 後來，SEC[修正](https://www.sec.gov/rules/interp/34-47806.htm)了 17 CFR 240.17 a-4 段落（f），它會明確發出兩個 interpretive 發行，以允許在符合特定條件時，在電子儲存介質上保留書和記錄。

如果電子儲存系統在必要的保留期間內禁止變更或擦除記錄，則會符合這些條件。 保留期間會根據記錄類型的不同三到六年而定，且前兩年立即可存取性規定。 此外，其中一個 interpretive 版本需要儲存系統能夠保留超過 SEC 既定保留期的記錄，以遵守 subpoenas、法律封存或其他此類需求。

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft 和 SEC Rule 17a-4 （f）

金融服務客戶（如世界上最受管制的行業之一）受到複雜的置備，例如保留金融交易和相關通訊的非擦除和不可修改的狀態。 最具規範性的是美國證券和 Exchange 傭金（SEC）的規則17a-4，stipulates 對管制實體所做的嚴格需求，以選擇在電子化儲存介質上保留書籍和記錄。 儲存的記錄必須防篡改，但不能變更或刪除，直到指定的保留期間為止。

Microsoft Azure 永恆 Blob 儲存 with Policy Lock 和 Microsoft Office 365 （含保留鎖定）可協助金融機構符合 SEC Rule 17a-4 （f）的不可變儲存需求。

若要評估 Azure 與 Office 365 符合 SEC Rule 17a-4 （f），Microsoft 保留了獨立的評估事務所，專門從事記錄管理和資訊管理，Cohasset 關聯。 在結果報告中：

- **Azure**： [SEC 17a-4 （f）合規性評估： Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)，Cohasset 使用原則鎖定選項驗證[Azure 不可變化的 blob 儲存](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage)，當用來保留非擦除和不可讀寫（WORM）格式的時間範圍內的 blob 時，會滿足 SEC 規則的不可變化的儲存需求。 每個 Blob （記錄）都會受到保護，無法進行修改、覆寫或刪除，直到必要的保留期間到期併發行任何關聯的合法保留期間為止。 具有敏感工作負載的軟體提供者和合作夥伴現在可以依靠 Azure 不可變化的 Blob 儲存為 onestop 雲端方案，以進行記錄保留和不可變的儲存。 金融機構現在可以組建自己的應用程式，利用這些功能，並保持不相容。
- **Office 365**：[使用 Exchange ONLINE 來符合 SEC 17a-4](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4)，Cohasset 已驗證[具有保留鎖定的 Office 365](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)包含封存功能，可讓受管制的客戶（包括經紀人代理商）儲存資料，以協助其遵守記錄保留的 SEC 需求。 Office 365 中的保留原則有助於保留大量的資料，包括電子郵件、語音信箱、共用檔、立即訊息和協力廠商資料。 具體而言，Office 365 中的封存可讓客戶設定全域或細微的郵件保留原則，以儲存定義期間的資料，而不是以不可重寫的 nonerasable 格式。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>稽核、報告和認證

### <a name="azure--sec-rule-17"></a>Azure & SEC 規則17

[SEC 17a-4 & CFTC 1.31 （c-d） Azure Storage 的相容性評估](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Office 365 & SEC 規則17

[SEC 17a-4 （f）合規性評估： Microsoft Security & 合規性中心與 Exchange Online](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>實施方式

### <a name="financial-services-regulation"></a>金融服務法規

適用于雲端計算和 Microsoft online 服務之重要的 US 規章原則的符合性地圖。 [深入了解](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>風險評估 & 規範指南

建立管理模型，以用於 Microsoft 雲端服務的風險評估，以及調壓器通知。 [深入了解](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>財務使用案例

使用案例概述、教學課程及其他資源，建立用於金融服務的 Azure 解決方案。 [深入了解](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>資源

- [在 Microsoft Office 365、資料保留和規則17a-4 中封存](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)
- [規範 Microsoft 金融服務](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [規範計畫 Microsoft business cloud 服務和金融服務](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure 的金融服務合規性](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融服務雲端風險評定工具](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 保留原則](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融服務部落格](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
