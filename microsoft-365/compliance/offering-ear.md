---
title: 美國匯出管理法規 （耳朵上）
description: Microsoft 雲端服務可協助客戶受限於美國匯出管理法規 （耳朵上） 符合其合規性需求，以及管理匯出控制項風險。
keywords: Microsoft 365、 規範、 供應項目
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 283b6a45807547f9a8d0521cf2c6793a2a15c4d6
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690278"
---
# <a name="compliance-offering-us-export-administration-regulations-ear"></a>合規性供應項目： 美國匯出管理法規 （耳朵上）

## <a name="about-the-ear"></a>關於耳朵上

美國部門的商務強制使用匯出管理法規 （耳朵上） 透過[部門的產業和安全性 (BIS)](https://www.bis.doc.gov/)。 耳朵上廣泛地管理，並會有所匯出與重新匯出的大部分的商業性商品、 軟體和技術，包括 「 雙重使用 」 項目可以用於同時進行商業和軍事和國防版中的特定項目上的控制項。

BIS 指引保留，當資料或軟體是上傳至雲端，或使用者節點之間轉換，客戶，不雲端提供者，就是 「 匯出工具 」，負責確保可轉接的、 儲存，與該資料或軟體的存取權遵守耳朵。

[根據 BIS](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file)，*匯出*指的是受保護的技術或技術資料傳輸到外部目的地或其釋出到外部人員 （也稱為*感測器，匯出*） 的美國。 耳朵上廣泛地管理：

- 從美國匯出。
- 重新匯出或 retransfers 美國原點的項目及具有多個美國原點內容*de minimis*部分特定外部來源項目。
- 轉接或從其他國家/地區提供給者且揭露。

在商務控制清單 (CCL) 其中每個項目指派唯一[匯出控制項分類數字 (ECCN)](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn)可以找到受到耳朵上的項目。 項目未列於 CCL 都會指定為 EAR99 和大部分 EAR99 商業產品不需要要匯出的授權。 不過，根據目的地、 使用者或項目的結尾用途，即使 EAR99 項目可能會需要 BIS 匯出授權。

[最後一個規則](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations)，在 2016 年 6 月中，發佈釐清也授權需求的耳朵上不會套用至傳輸和儲存未分類的技術資料，以及軟體如果它們已加密的端對端使用 FIPS 140-2 已驗證的密碼編譯模組和已不是刻意儲存於軍事貿易國家/地區或俄文同盟。

## <a name="microsoft-and-the-ear"></a>Microsoft 和耳朵上

Microsoft 技術、 產品及服務會受限於美國匯出管理法規 （耳朵上）。 針對耳朵上不符合性憑證時，提供重要功能和工具，以協助耳朵上受到合格客戶管理匯出的 Microsoft Azure、 Microsoft Azure 政府和 Microsoft Office 365 政府版 （GCCHigh 和 DoD 環境）控制風險，且符合其合規性需求。

美國商務部門，強制執行耳朵上，已採取客戶，雲端 Microsoft，例如服務提供者會被視為是匯入程式自己客戶資料的位置。 雖然大部分的客戶資料不會被視為 「 技術 」 或 「 技術資料 」 受到耳朵上匯出控制項，Microsoft 範圍內的雲端服務的結構可協助客戶管理，並會大幅降低所面臨的潛在匯出控制項風險。 Microsoft 通常，但未以獨佔模式，建議使用的合格客戶其政府雲端服務。 有適當的規劃，客戶可以使用下列工具和自己內部的程序，以協助確保完整遵守美國匯出的控制項。

- **在 [資料位置上的控制項**。 客戶可有其資料儲存位置的可視性和強大的工具，以限制其儲存裝置的存取。 它們可能會因此會確保其資料儲存在美國及降至最低的受控制的技術或在美國的技術資料傳輸。 此外，客戶資料不會儲存在不合格的位置，與在何處耳朵上 prohibitions 一致的資料 」 是刻意儲存 「: 沒有 Azure 資料中心位於任何 25 群組 D:5 國家/地區或俄文同盟。
- **端對端加密**。 利用中耳朵上指定的實體儲存位置的端對端加密安全港，Microsoft 範圍內的雲端服務會傳送的加密功能，可協助防止匯出控制項風險。 他們也提供客戶[各式各樣的選項來加密資料](https://aka.ms/Azure-Encryption-Overview)傳輸中和 rest、 及彈性來選擇加密選項。
- **工具和通訊協定以防止未經授權會被視為匯出**。 使用加密也可協助防止潛在的 deemed 匯出 （或重新匯出會被視為） 底下耳朵上，因為偶數如果非美國的人的存取權可 nothing 加密資料，隨著如果無法讀取或了解時的資料就會被加密;因此沒有任何 「 版本 」 控制的資料。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內的雲端服務

- [Azure 和 Azure 政府版](https://aka.ms/AzureCompliance)
- [Office 365 政府版 （GCC 高和 DoD）](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>如何實作

我們概觀匯出控制項和評估下耳朵上其義務的客戶的指引。

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>常見問題集

**遵守匯出控制項，使用 Microsoft 雲端服務時該怎麼辦？**

下耳朵上，當資料上傳到雲端伺服器，例如 Microsoft cloud，擁有資料的客戶 — 非的雲端服務提供者 — 會被視為匯出工具。 基於這個理由，資料的擁有者--亦即，Microsoft 客戶 — 必須仔細評估其使用的 Microsoft cloud 可能 implicate 我們匯出的控制項，並判斷是否有任何他們想要使用或有儲存的資料可能會受到耳朵上控制項而且如果有哪些控制項，請套用。 了解[Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)與[Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI)雲端服務如何協助確保其完整的合規性美國的客戶匯出的控制項。

**限於耳朵上的 Microsoft 技術、 產品及服務？**

大部分的 Microsoft 技術、 產品及服務下列一項：

- 不耳朵上的主旨和因此不在 [商務控制項清單中，且有無 ECCN;
- 或他們 EAR99 或 5D992 大量市場合格的 microsoft 自我分類和可能匯出至非貿易國家/地區沒有授權為否授權所需 (NLR)。

也就是說，已指派一些 Microsoft 產品 ECCN，可能有或可能不需要授權。 請參閱耳朵上或法律顧問，以決定適當的授權類型及合格的國家/地區的將匯出的目的。

**和之間的差異耳朵上國際流量中武器法規 (ITAR) 是什麼？**

美國匯出如果控制項具有廣泛的應用程式的主要是耳朵上，由商務美國部門所管理。 耳朵上可套用至使用雙重使用具商業和軍事應用程式的項目，並與純粹商業應用程式的項目。

美國還有個別和多特製化匯出控制項法規，ITAR，最機密的項目與技術，例如。 他們管理由美國部門的狀態，會強制控制項匯出、 暫存匯入、 重新匯出，並傳輸的許多軍事單位、 國防版及智慧項目 （也稱為 「 深層文章 」），包括相關的技術資料。

## <a name="resources"></a>資源

- [匯出 Microsoft 產品： 概觀](https://www.microsoft.com/exporting/overview.aspx)
- [匯出 Microsoft 產品： 常見問題集](https://www.microsoft.com/exporting/faq.aspx)
- [匯出的 Microsoft 產品： 產品查閱](https://www.microsoft.com/exporting/exporting-information.aspx)
- [匯出密碼編譯的限制](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft 和 FIPS 140-2](offering-fips-140-2.md)
- [Microsoft 和 ITAR](offering-itar.md)
- [在 Microsoft 信任中心合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
