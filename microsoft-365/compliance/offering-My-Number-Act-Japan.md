---
title: 個人編號法案 (My Number Act) (日本)
description: Microsoft 商務雲端服務遵循「個人編號法案」標準，以保護「個人編號」資料的隱私權。
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
ms.openlocfilehash: a2ef9ff0521755bbb3000dd42b417ff57e398bbb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602130"
---
# <a name="my-number-act-japan"></a>個人編號法案 (日本)

## <a name="about-the-my-number-act"></a>關於「個人編號法案」

日本政府頒布「個人編號法案」([日文版](https://elaws.e-gov.go.jp/search/elawsSearch/elaws_search/lsg0500/viewContents?lawId=425AC0000000027_20180627_430AC0000000066)和[英文版](https://www.ppc.go.jp/files/pdf/en3.pdf))，並於 2016 年 1 月生效。 該法案為每位日本居民 (無論是日本人或外國人) 指派一組專屬的 12 位數編號，也稱為「個人編號」、「社會保障編號」和「稅籍編號」或「個別編號」。 給予每位人員一組編號 (例如美國社會安全編號) 的目的，在於簡化並提高稅捐稽徵處效益和社會安全福利的實作，例如國民年金、醫療保險和失業救濟。

個人資訊保護委員會 (PPC) 身為集中式資料保護機構，是根據「個人資訊保護法案」([日文版](https://www.ppc.go.jp/personal/preparation/)和[英文版](https://www.ppc.go.jp/en/legal/)).所建立。 PPC 的角色為監管及監視與「個人編號法案」的合規性，其已頒布 [「個人編號」指引](https://www.ppc.go.jp/legal/policy/faq/) (日文版)，以確保組織適當地處理並合宜保護個人資料，包括法律所要求的「個人編號」資料。

## <a name="microsoft-and-the-my-number-act"></a>Microsoft 和「個人編號法案」

為了協助日文客戶保護個人資料的隱私權，Microsoft 按照合約透過 [Microsoft Online Services 條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)，致力於確認我們的範圍內商務雲端服務已實作技術和組織安全性保護機制，可協助客戶符合「個人編號法案」。這表示日本客戶在部署 Microsoft 商務雲端服務，可以具備其將遵循日本法規需求的信心。

由個人資訊保護委員會 (PPC) 發佈的 [Q\&A](https://www.ppc.go.jp/legal/policy/faq/) (日文版)，規定了適當處理並保護個人資料的指引。 其指出如果第三方在合約中規定 (a) 不如此做，並且 (b) 建立適當的存取控制系統，則不能將其解釋為處理個人資料。 「個人編號法案」指定資料轉移給第三方時的義務，但是 PPC Q\&A 之 [Q3-12](https://www.ppc.go.jp/legal/policy/faq/) (日文版) 章節解釋了如果第三方沒有「處理」(即存取) 個人資料時，則這些不適用。

Microsoft 商務雲端服務在 [Microsoft Online Services 條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)中說明了這些需求，規定了包含「個人編號」資料的客戶資料的責任和擁有權屬於客戶，而非 Microsoft。 客戶因此必須具備適當的控制措施，以保護客戶資料中所包含的「個人編號」資料。

因為 Microsoft 無法存取儲存於雲端服務中的「個人編號」資料，所以不需要處理「個人編號」資料的「委外」合約。 如果客戶希望 Microsoft 具有存取包含「個人編號」資料的的客戶資料，客戶必須先與 Microsoft 針對每個案例先建立額外的委外合約，才能提出這樣的要求。

這項條款也陳述 Microsoft 致力於使用客戶資料僅用來提供客戶服務，而非任何廣告或類似的商業用途，並且 Microsoft 已具備強健的存取控制系統。

針對安全性疑慮，Microsoft 商務雲端服務符合[雲端安全性標記 (金色)](offering-cs-mark-gold-japan.md) 標準，此為日本第一個雲端服務提供者的安全性認證。

因此，Microsoft 商務雲端服務支援「個人編號法案」的需求，並不會以客戶之名建立其他義務，(例如由個人資料個別擁有者的同意權)。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Dynamics 365](https://download.microsoft.com/download/E/1/9/E1977163-7A86-4812-AC18-C03ADC958AAF/Microsoft_Dynamics_365_Cloud_Service_Compliance_Datasheet.pdf)
- Intune
- [Office 365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9f756cce-b15d-45a9-94d7-6a583dee4401&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

## <a name="how-to-implement"></a>實作方法

- [Microsoft 安全性原則](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=231213ea-9954-41fd-a757-ae62f3721dc7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)：Microsoft 雲端服務中處理個人和組織資訊安全性的方法。

- [Office 365 中的隱私權](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=a1b48a5b-bcb1-4c19-9277-952c0df87113&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)：Microsoft 如何在 Office 365 中建構強大的隱私權保護。

- [Office 365 中系統管理存取](https://docs.microsoft.com/office365/SecurityCompliance/office-365-administrative-access-controls-overview)：Microsoft 如何管理對Office 365 客戶數據的系統管理存取。

- [Office 365 中的稽核與報告](https://docs.microsoft.com/office365/SecurityCompliance/office-365-auditing-and-reporting-overview)：探索客戶可用來追蹤其租用戶中使用者和系統管理活動的功能。

- [Office 365 中的資料保留](https://docs.microsoft.com/office365/SecurityCompliance/office-365-data-retention-deletion-and-destruction-overview)：了解刪除資料後，客戶資料保留時間之資料處理原則。

## <a name="frequently-asked-questions"></a>常見問題集

**在「個人編號法案」中，何者具有保護個人資料的終極責任？**

PPC Q\&A 的 [Q3-13 章節](https://www.ppc.go.jp/legal/policy/faq/) (日文版) 陳述因為個人資料的擁有權在 Microsoft 客戶身上，他們必須採取適當的安全性措施，例如控制系統管理員密碼，以保護個人資訊和「個人編號」資料。

## <a name="resources"></a>資源

- [Azure 合規性和日本安全性與隱私權需求](https://gallery.technet.microsoft.com/Azure-Compliance-and-the-53409748)
- [Microsoft 中的隱私權](https://privacy.microsoft.com/en-US/)
- [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)
- [雲端隱私權考量](https://download.microsoft.com/download/0/9/D/09DE47F6-F9E5-4C14-B9E8-E8119A130ACC/Privacy_considerations_in_the_cloud.pdf)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下載方案背景資料

是否需要此方案的背景資料文件？ 下載 [PDF](https://download.microsoft.com/download/0/E/C/0EC14DDA-6041-4841-A180-199870B136C4/MyNumberAct-Compliance.pdf)。
