---
title: " (EAR) 美國出口管理條例"
description: Microsoft 雲端服務可協助客戶遵循美國出口管理法規 (EAR) 符合其相容性需求和管理出口控制風險。
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
ms.openlocfilehash: 4ad12f785a76f6ee733cb3b459ad58370a330f51
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416059"
---
# <a name="us-export-administration-regulations-ear"></a> (EAR) 美國出口管理條例

## <a name="about-the-ear"></a>關於 EAR

華南商務系會透過 [工業和 Security (BIS) 的局， ](https://www.bis.doc.gov/)強制實施 (EAR) 的出口管理條例。 EAR 對大多數商業商品、軟體及技術（包括可用於商業和軍事的目的和某些防護專案）的出口和重新出口，都有廣泛的控制和強加控制。

BIS 指導方針：將資料或軟體上傳至雲端或在使用者節點之間傳輸時，客戶（而非雲端提供者）是「匯出者」，其負責確保資料或軟體的轉移、儲存和存取權符合 EAR。

[根據 BIS](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file)，「 *出口* 」指的是將受保護的技術或技術資料到外部目的地或其版本轉讓給美國的國外人員 (也稱為「 *出口*) 」。 《 EAR 的廣泛管理：

- 從美國出口。
- 重新匯出或 retransfers 美國原產地專案和某些外部來源專案，其具有超過 minimis 的我們原始內容的 *de* 。
- 對其他國家/地區的人員進行轉接或披露。

您可以在商務控制項清單 (CCL) 上找到該 EAR 的專案，而每個專案都有指派唯一的 [匯出控制項分類號碼 (ECCN) ](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn)。 CCL 中未列出的專案會被指定為 EAR99，而大部分 EAR99 商業產品不需要匯出授權。 不過，根據目的地、使用者或專案的結束用途，甚至 EAR99 專案也可能需要 BIS 出口授權。

在2016年6月發行的 [最後一項規則](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations)闡明瞭 EAR 授權需求也不會套用到未分類的技術資料和軟體的傳輸和儲存，如果他們使用 FIPS 140-2 驗證的密碼編譯模組，而且不是特意儲存在軍事禁運的國家或俄羅斯同盟中。

## <a name="microsoft-and-the-ear"></a>Microsoft 和 EAR

Microsoft 技術、產品和服務受到美國出口管理條例 (EAR) 的制約。 雖然沒有 EAR 的相容性認證，但 Microsoft Azure、Microsoft Azure 政府和 Microsoft Office 365 政府 (GCCHigh 和 DoD 環境) 提供重要的功能和工具，以協助符合 EAR 管理出口控制風險和符合其符合性需求的合格客戶。

強制執行 EAR 的 US 商務部門，已將客戶（而非雲端服務提供者，例如 Microsoft）的位置視為 exporters 自身的客戶資料。 雖然大多數客戶資料不會被視為「技術」或「技術資料」受 EAR 出口控制，但 Microsoft 範圍內的雲端服務會加以組織，以協助客戶管理並大幅緩解其所面臨的潛在出口控制風險。 Microsoft 通常（但非獨佔）建議使用其適用于合格客戶的政府雲端服務。 透過適當的規劃，客戶可以使用下列工具和自己的內部程式，協助確保完全符合美國出口控制項。

- **資料位置上的控制項**。 客戶可以查看其資料的儲存位置，並存取強健的工具來限制其儲存空間。 因此，他們可能會確定其資料儲存在美國，並最小化美國境外的受控技術或技術資料的轉接。 此外，客戶資料不會儲存在不相容的位置，與 EAR prohibitions （資料是「特意儲存」）一致：沒有任何 Azure 資料中心位於25群組 D:5 國家或俄文同盟中的任何一個。
- **端對端加密**。 透過利用 EAR 中所指定實體儲存位置的端對端加密安全實體，Microsoft in 範圍雲端服務會提供可協助防範出口控制風險的加密功能。 他們也為客戶提供 [廣泛的選項](https://aka.ms/Azure-Encryption-Overview) ，可在傳輸和靜止中加密資料，以及在加密選項之間選擇的彈性。
- **工具和通訊協定，可防止未經授權的人認定匯出**。 使用加密，也有助於防範可能受到認定的匯出 (或被視為在 EAR 下重新匯出) ，因為即使非 US 人員可以存取加密的資料，也不會發現或在加密時無法讀取或瞭解資料時，什麼都不會顯示。因此，控制的資料沒有「發行」。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure 和 Azure Government](https://aka.ms/AzureCompliance)
- [Office 365 政府 (GCC-高和 DoD) ](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>實作方法

在 EAR 中，針對客戶評估其義務的 [美國出口] 控制項與指引。

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>常見問題集

**使用 Microsoft 雲端服務時，應如何遵守匯出控制項？**

在 EAR 下，當資料上傳至雲端伺服器（例如 Microsoft 雲端）時，擁有資料的客戶（而非雲端服務提供者）會被視為匯出程式。 因此，資料擁有者（也就是 Microsoft 客戶）必須認真評估其使用 Microsoft 雲端的方式。我們可以 implicate US export 控制項，並判斷是否有任何想要使用或儲存的資料可能會受到 EAR 控制，如果是的話，也可以套用哪些控制項。 深入瞭解 [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) 和 [Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI) 雲端服務可如何協助客戶確保其與美國出口控制項完全相容。

**Microsoft 技術、產品及服務是否受 EAR 的制約？**

大多數的 Microsoft 技術、產品和服務，都包括：

- 不受制于 EAR，因此不會在商務用控制項清單中，也沒有任何 ECCN。
- 或者是 EAR99 或5D992 大量市場，可供 Microsoft 自行分類，而且可能會匯出至非禁運國家/地區，但不需要授權 (NLR) 。

也就是說，有些 Microsoft 產品已獲指派 ECCN，可能需要，也可能不需要授權。 請諮詢 EAR 或法律顧問，以判斷出口用途的適當授權類型和合格國家/地區。

**在 Arm 法規 (ITAR) 中，EAR 和國際流量之間的差異為何？**

主要美國的美國出口控制，其應用程式是由美國商務系公司管理的耳。 這種 EAR 適用于同時具有商業性和軍事應用程式的雙用途專案，以及純商業應用程式的專案。

美國還有個別的和更多專用的出口控制法規（如 ITAR），可控制最機密的專案和技術。 由美國的省/州（美國）系所管理，可對許多軍用、國防和智慧 (專案（也稱為「國防文章」） ) （包括相關的技術資料）進行出口、暫時匯入、重新匯出及傳輸。

## <a name="resources"></a>資源

- [匯出 Microsoft 產品：簡介](https://www.microsoft.com/exporting/overview.aspx)
- [匯出 Microsoft 產品： FAQ](https://www.microsoft.com/exporting/faq.aspx)
- [匯出 Microsoft 產品：產品查閱](https://www.microsoft.com/exporting/exporting-information.aspx)
- [匯出密碼編譯限制](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft 和 FIPS 140-2](offering-fips-140-2.md)
- [Microsoft 和 ITAR](offering-itar.md)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
