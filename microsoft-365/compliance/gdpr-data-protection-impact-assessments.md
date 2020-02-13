---
title: 資料保護影響評估
description: 這些文件提供資料控制者資訊，協助他們判斷是否需要 DPIA，以及若需要，應包含哪些詳細資料。
keywords: 資料保護影響評估, DPIA, Dynamics 365, Microsoft Professional Services, Microsoft 365, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0a62cf2ef40bbf9da219309cf75eed27ea8739e4
ms.sourcegitcommit: 2498cd4af90c31771167a1be9f8f12a96dc6500f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41916898"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a>GDPR 資料保護影響評估

針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處都必須遵守。 您可以在 [GDPR 摘要主題](gdpr.md)中找到其他詳細資料。 這份文件將引導您在使用 Microsoft 產品和服務時，取得 GDPR 規定下之資料保護影響評估 (DPIAS) 的相關資訊。

## <a name="terminology"></a>術語

本文件中使用的 GDPR 術語的實用定義：

- 資料控制者 (控制者)**：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。  
- 個人資料** 和資料主體**：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。  
- 處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。  
- *客戶資料*：在公司運作的日常作業中產生並儲存的資料。

## <a name="what-is-a-dpia"></a>什麼是 DPIA？

GDPR 需要控制者為「可能導致自然人之權利和自由高風險」的作業準備資料保護影響評估 (DPIA)。 Microsoft 產品和服務中沒有需要 DPIA 建立的項目。 不過由於 Microsoft 產品和服務的高度可自訂性，根據您的 Microsoft 設定之詳細資料可能因此會需要 DPIA。 Microsoft 無法控制，並對這些資訊沒有任何了解。 身為資料控制者的您必須決定資料的正確使用。

## <a name="dpia-in-action"></a>DPIA 實際運作方式

DPIA 指導方針適用於 Office 365、Azure、Dynamics 365，和 Microsoft 支援服務及專業服務。 指導方針包含考量：

**何時需要 DPIA？**

考慮是否要完成 DPIA 時，應設法解決以下風險因素。 每個指導方針的第 1 部分可找到其他潛在因素與進一步詳細資料。  

- 基於自動化處理之資料的系統化和廣泛評估。  
- 處理大規模的特殊類別資料 (顯示唯一識別自然人資訊的資料) 或與刑事定罪和犯罪相關的個人資料。
- 系統化監視大規模的公開區域。

GDPR 闡明：「如果處理是有關於個別醫生的病患或其他醫療保健專業人員或律師之客戶的個人資料，則處理個人資料不應視為大規模。 在此類情況下，資料保護影響評估不應強制」。

**完成 DPIA 的必要項目？**

根據本指導方針第 2 部分的詳細說明，DPIA 必須提供欲處理作業的特定資訊。 這些資訊包含：

- 評估與 DPIA 目的相關之資料處理的必要性和相稱性。  
- 評估自然人的權利和自由風險。
- 意圖解決風險的措施，包含防護措施、安全性措施，和確保個人資料保護並證明遵守 GDPR 的機制。
- 處理目的  
- 處理的個人資料類別  
- 資料保留  
- 個人資料的位置和傳輸  
- 與第三方子處理者共用資料  
- 與獨立第三方共用資料  
- 資料主體權利

## <a name="additional-considerations"></a>其他考量

以下是可能與您的 Microsoft 實作的特定詳細資料。

- [Office 365](gdpr-dpia-office365.md)：這份文件適用於 Office 365 應用程式和服務，包含但不限於 Exchange Online、SharePoint Online、Yammer、商務用 Skype 和 Power BI。 如需詳細資訊，請參閱表 [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) 與 [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)。  
- [Azure](gdpr-dpia-azure.md)：我們鼓勵客戶與其隱私權主管和法律顧問合作，以確定與使用 Microsoft Azure相關之任何 DPIA 的必要性和內容。  
- [Dynamics 365](gdpr-dpia-dynamics.md): DPIA 的內容可能根據您採用的 Dynamics 365 工具而有所不同。 如需特定詳細資料，請參閱[第 2 部分：DPIA 的內容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia)。
- [Microsoft 支援服務及專業服務](gdpr-dpia-prof-services.md)：專業服務不會進行特定常式或自動的資料處理，也不會試圖處理特殊類別，或執行促進或需要監管公開資料的任務。 如需詳細資料，請參閱[第 1 部分 – 判斷是否需要 DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed)。 在控制者的特定實作與專業服務的使用情況下，控制者必須考慮上述的 DPIA 元素以及其他相關因素。 如需專業服務的詳細資訊，請參閱[第 2 部分：DPIA 的內容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia)。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
