---
title: 金融行業規章機關 (FINRA) 規則 4511 (c) 美國
description: 獨立評估公司已驗證，Azure 和 Office 365 可協助財務公司符合 FINRA 規則4511記錄保留和不可變的儲存需求。
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
ms.openlocfilehash: 2ba5dc4726f359545d59de7387fc62a3fe897588
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995886"
---
# <a name="financial-industry-regulatory-authority-finra-rule-4511c-united-states"></a>金融行業規章機關 (FINRA) 規則 4511 (c) 美國

## <a name="about-finra-rule-4511"></a>關於 FINRA 規則4511

[財務行業的規章管制機關 (FINRA) ](https://www.finra.org/#/)是控制證券公司的最大獨立主體，並在美國監管超過4500的經紀公司。 他是由美國國會所授權，可確保經紀人行業的運作既公平又誠實，以保護美洲的投資者。

在2011中，US 證券和 Exchange 傭金 (SEC) 核准 FINRA 採用，以管理電子儲存介質上的書和記錄的保留。 [FINRA Rule 4511 (c) ](https://www.finra.org/sites/default/files/NoticeDocument/p123548.pdf) 指定「必須依照符合海運 (證券 Exchange 法案) Rule-4 的格式和媒體，保留「FINRA 規則」所需的「所有手冊和記錄」。

此外，FINRA Rule 4511 (c) 要求公司至少保留六年的圖書和記錄，這些書和記錄在適用的 FINRA 或海平面規則下沒有指定的保留期間。 實際上，如果書籍和記錄屬於某個帳戶，保留期間會規定在帳戶關閉之後六年。 否則，保留期間是在這類書和記錄建立之後六年之後。

## <a name="microsoft-and-finra-rule-4511c"></a>Microsoft 和 FINRA 規則 4511 (c) 

金融服務客戶（如世界上最受管制的行業之一）受到複雜的置備，例如保留金融交易和相關通訊的非擦除和不可修改的狀態。 其中包括財務行業規章機關的規則 4511 (FINRA) ，可 stipulates 所需的管制實體需求，以在電子化儲存介質上保留書和記錄。 儲存的記錄必須防篡改，但不能變更或刪除，直到指定的保留期間為止。

Microsoft Azure 永恆 Blob 儲存 with Policy Lock 和 Microsoft Office 365 （含保留鎖定）可協助金融機構符合 FINRA 規則 4511 (c) 中不可變的儲存需求。

## <a name="microsoft-azure"></a>Microsoft Azure

若要評估 Azure 與 FINRA 規則4511的相容性 (c) 中，Microsoft 保留了專門從事記錄管理和資訊管理、Cohasset 關聯的獨立評估事務所。 產生的報告、 [SEC 17a-4 (f) & CFTC 1.31 (的 FINRA) 相容性評估： Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)，包含 Azure 相容性與規則 4511 (c) ，這會符合 SEC Rule 17a-4 (f) 的格式和媒體需求。

Cohasset 使用原則鎖定選項驗證 [Azure 不可變化的 Blob 儲存](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) ，當用來保留非擦除和不可讀寫 (WORM) 格式的時間內的 blob 時，就會符合相關的 FINRA 儲存需求。 每個 Blob (記錄) 都會受到保護，無法進行修改、覆寫或刪除，直到必要的保留期間到期併發行任何關聯的合法保留期間為止。

具有敏感工作負載的軟體提供者和合作夥伴現在可以依靠 Azure 不可篡改的 Blob 存放區儲存為記錄保留和不可變化存放區的一個停止車間雲端方案。 金融機構現在可以組建自己的應用程式，利用這些功能，並保持不相容。

## <a name="microsoft-365"></a>Microsoft 365

針對 [FINRA 4511 (c) ](retention-regulatory-requirements.md#sec-17a-4f-finra-4511c-and-cftc-131c-d) 需求，Cohasset 驗證 Microsoft 365 包含的封存功能可讓受管制的客戶（包括經紀人代理商）儲存資料，以協助其遵守記錄保留的 SEC 需求。 Microsoft 365 中的保留功能可協助保留大量的資料，包括電子郵件、語音信箱、共用檔、立即訊息和協力廠商資料。 具體說來，在 Microsoft 365 中的封存可讓客戶設定全域或細微的郵件保留原則，以儲存定義期間的資料，而不是以不可重寫、不可讀寫的格式使用。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>稽核、報告和憑證

### <a name="azure--finra-rule-4511c"></a>Azure & FINRA 規則 4511 (c) 

[SEC 17a-4 (f) & CFTC 1.31)  (Azure 儲存體的相容性評估](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--finra-rule-4511c"></a>Office 365 & FINRA 規則 4511 (c) 

[Office 365 中的封存、資料保留及 SEC 規則17a-4 規範](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)

## <a name="how-to-implement"></a>實作方法

- **金融服務法規** ：適用于雲端計算和 Microsoft online 服務之重要的 US 規章原則的符合性地圖。 [深入了解](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- **風險評定與合規性指南** ：建立 Microsoft 雲端服務風險評定的監管模型和調整通知。 [深入了解](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- **金融使用案例** ：使用案例概覽、課程及其他資源建立適用於金融服務的 Azure 解決方案。 [深入了解](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>資源

- [Microsoft 金融服務合規性計劃](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Microsoft 商務用雲端服務與金融服務](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure 的金融服務合規性](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融服務雲端風險評定工具](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 保留原則](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融服務部落格](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
