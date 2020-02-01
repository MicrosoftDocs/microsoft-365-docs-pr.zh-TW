---
title: 規則 17a-4(f) 美國證券與 Exchange 委員會 （秒）
description: 獨立評估公司驗證 Azure 與 Office 365 可協助符合 SEC Rule 17a-4(f) 記錄保留與固定的儲存需求的財務公司。
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
ms.openlocfilehash: 5bbc8e8e39e28a020864d705489d704acd0c012b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602060"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>規則 17a-4(f) 美國證券與 Exchange 委員會 （秒）

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft 和 SEC Rule 17a-4(f)

[美國證券和 Exchange 委員會 （秒）](https://www.sec.gov/)是美國聯邦政府和主要領導人及調整的美國證券市場的獨立機構。 透過聯邦證券法律鑄造執法機構、 提出新的證券規則，以及監督的證券業的市場規定。

秒定義嚴格和明確需求管制的實體，選擇要保留活頁簿和電子儲存媒體上的記錄。 它建立[17 CFR 240.17a-3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3)和[17 CFR 240.17a-4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64)來調整 recordkeeping，包括美國證券業代理人協會保留期間。 稍後，秒[速度](https://www.sec.gov/rules/interp/34-47806.htm)17 CFR 240.17a-4 段落 (f)、 發出明文以允許活頁簿和記錄，以保留電子儲存媒體上，只要在符合特定條件的兩個 interpretive 版本。

電子儲存系統符合這些條件，如果它會防止被變更或清除記錄所需的保留期間。 保留期間會有所不同三個根據記錄類型，以立即存取範圍指定第一個兩年六個年。 此外，下列其中一個 interpretive 版本要求的儲存系統必須能夠保留超過秒建立的保留期間遵守 subpoenas、 法務保存措施或其他這類需求的記錄。

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft 和 SEC Rule 17a-4(f)

財務服務的客戶，表示下列其中一個領域中受到最嚴厲管制產業受限於複雜的佈建像保留金融交易和相關的通訊中的非可清除與非可修改的狀態。 之間最規定是美國安全性和 Exchange 委員會 （秒） 的規定嚴苛的需求，選擇要保留活頁簿和電子儲存媒體上的記錄的管制實體的規則 17a-4(f)。 儲存的記錄必須竄改與沒有變更或刪除它們之後指定的保留期間內的能力。

Microsoft Azure 不變的 Blob 儲存與原則鎖定和 Microsoft Office 365 with 保留鎖定有助於金融機構符合 SEC Rule 17a-4(f) 不變的儲存需求。

若要評估與 SEC Rule 17a-4(f) Azure 與 Office 365 合規性，Microsoft 保留獨立評估公司專門進行記錄管理及資訊治理規範，Cohasset 會產生關聯。 在產生報告：

- **Azure**:[秒 17a-4(f) 合規性評估： Microsoft Azure 儲存體](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)，Cohasset 驗證[Azure 不變的 Blob 儲存體](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage)使用原則鎖定選項時，用來保留時間為基礎的 Blob，以非可清除與非可讀寫的 （蠕蟲） 格式時, 符合秒規則不變的儲存需求。 每個 Blob （記錄） 受到防止修改、 覆寫，或刪除之前所需的保留期間已經過期和已釋放任何關聯的合法持有。 軟體提供者和機密的工作負載的協力廠商可以立即自信地仰賴 Azure 不變的 Blob 儲存體做為保留記錄與固定儲存 onestop 商店雲端解決方案。 金融機構現在可以建置自己運用這些功能時剩餘相容的應用程式。
- **Office 365**:[使用 Exchange Online 與秒 17a-4 Comply](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4)，Cohasset 證的[保留鎖定與 Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy)也包含封存功能，可讓受管制的客戶，包括代理人協會，來儲存資料的方式，可協助他們符合秒記錄保留需求。 Office 365 中的保留原則協助保留廣泛的資料，包括電子郵件、 語音信箱、 共用文件、 立即訊息和協力廠商資料。 特別是，在 Office 365 中封存可讓客戶若要設定全域或細微通訊保留原則，可將資料儲存在已定義的期間內和 beyond 非可重複燒錄、 nonerasable 的格式。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>稽核、報告和認證

### <a name="azure--sec-rule-17"></a>Azure # A0 SEC Rule 17

[秒 17a-4(f) & CFTC 1.31 (c-d) 合規性評估與目的的 Azure 儲存體](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Office 365 # A0 SEC Rule 17

[秒 17a-4(f) 合規性評估： 與 Exchange Online 的 Microsoft 安全性 & 合規性中心](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>實作方法

### <a name="financial-services-regulation"></a>財務服務規定

合規性對應的索引鍵的美國法規原則雲端運算與 Microsoft online services。 [深入了解](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>風險評定 & 合規性指南

建立風險評定的 Microsoft 雲端服務，並調整通知的控管模型。 [深入了解](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>財務使用案例

若要建置 Azure 解決方案的財務服務使用案例概觀、 教學課程，以及其他資源。 [深入了解](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>資源

- [在 [Microsoft Office 365、 資料保留和規則 17a-4 封存](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)
- [合規性 Microsoft 財務服務](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [合規性程式 Microsoft business 雲端服務和財務服務](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure 的金融服務合規性](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融服務雲端風險評定工具](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 保留原則](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融服務部落格](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下載方案背景資料

是否需要此方案的背景資料文件？ 下載 [PDF](https://download.microsoft.com/download/E/5/2/E52103E7-C1BB-4118-9725-4452FEA931D8/SEC17a-4(f)-Compliance.pdf)。
