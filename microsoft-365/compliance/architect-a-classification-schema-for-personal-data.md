---
title: 設計個人資料的分類結構描述
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 判斷您的組織是否將實作標籤做為 GDPR 計劃的一部分。
ms.openlocfilehash: db61c5c26ed8484e99aa8f06310bdd3385cf2dce
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637133"
---
# <a name="architect-a-classification-schema-for-personal-data"></a>設計個人資料的分類結構描述

本系列先前的文章著重於使用敏感資訊類型，識別受到 GDPR 約束的個人資料。敏感資訊類型是一種分類形式。這可能正是您需要的分類。不過，許多組織會使用標籤，實作更廣泛的資料控管策略。使用本主題，來決定您是否也想要實作標籤做為 GDPR 計劃的一部分。如果您這麼做，本主題提供一些指導方針和範例。

附註：定義組織的分類結構描述和設定原則、標籤和條件，需要仔細規劃和準備。了解這不是 IT 導向程序很重要。請務必與您的法律和合規性小組合作，為您組織的資料開發適當的分類與標示結構描述。

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a>決定您除了敏感性資料類型外是否也使用標籤

您可以在 Microsoft 365 中採取兩種方法對個人資訊進行分類。任一種都可用於 GDPR 保護。如果您決定僅使用敏感資訊類型進行分類，您可以跳過本主題的其餘部分。

選擇下列其中一個選項。

### <a name="option-1-use-only-microsoft-365-sensitive-information-types"></a>選項 1：僅使用 Microsoft 365 敏感資訊類型

- 敏感資訊類型非常適用於識別和保護受到 GDPR 和其他法規類型約束的個人資料。

- 如果您的組織尚未有敏感資訊類型，或打算使用標籤，實作更廣泛的資料控管計劃，則這些敏感資訊類型更易於使用。

- 這些敏感資訊類型會使用 DLP 規則 (保留標籤也一樣)。

- 敏感資訊類型可以搭配雲端 App 安全性一起使用，以便您可以偵測其他 SaaS 應用程式中的敏感資訊。

### <a name="option-2-use-sensitive-information-types--retention-labels"></a>選項 2：使用敏感性資訊類型 + 保留標籤

- 您將需要敏感資訊類型，才能對受限於 GDPR 的個人資料自動套用標籤，因此這些是必要的。

- 使用保留標籤可讓您將受到 GDPR 約束的個人資料併入更廣泛的資料控管計劃中。

## <a name="develop-a-label-schema-that-includes-personal-data"></a>開發包含個人資料的標籤結構描述

在使用技術功能來套用標籤和保護之前，於您的整個組織中首先定義分類結構描述。您的組織可能已有分類結構描述，可讓您更輕鬆地新增個人資料。本主題包含分類結構描述範例。必要時，您可以使用此範例做為起點。

### <a name="getting-started"></a>快速入門

從決定要實作之標籤的數目和名稱開始。執行此活動，不必擔心要使用哪種技術，以及將如何套用標籤。將此結構描述套用至您的整個組織，包括存放在內部部署以及其他雲端服務中的資料。

### <a name="recommendations"></a>建議 

設計和實作原則、標籤和條件時，請考慮遵循下列建議：

- 使用現有的分類結構描述 (如果有的話) &ndash; 許多組織已在使用某種形式的資料分類。仔細評估現有的標籤結構描述，並盡可能按原狀使用。利用使用者可以辨識的熟悉標籤將提高採用率。

- 從預設原則和標籤開始 &ndash; 所有解決方案都隨附一組預先定義的原則和標籤。針對組織法律和商務需求仔細評估這些原則和標籤，並考慮使用它們，而不建立新的原則和標籤。

- 從少量開始 &ndash; 可以建立的標籤數目幾乎沒有限制。不過，大量標籤和子標籤將對採用造成負面影響。太多選擇通常表示完全沒有選擇。

- 使用情節和使用案例 &ndash; 識別組織內常見的使用案例，並使用衍生自 GDPR 的情節，來驗證構想的標籤和分類設定是否實際可行。

- 每次要求新標籤時問自己 &ndash; 每個情節或使用案例真的需要新的標籤，還是可以使用已有的標籤？保持最少的標籤數目可以提高採用率。

- 對重要部門使用子標籤 &ndash; 某些部門將有需要特定標籤的特定需求。定義這些標籤做為現有標籤的子標籤，並考慮使用已指派給使用者群組，而不是全域指派的範圍限定原則。

- 考慮範圍限定原則 &ndash; 此為將使用者子集設為目標的原則，將防止「標籤超載」。範圍限定原則可讓您只將角色或部門特定 (子) 標籤指派給為特定部門工作的員工。

- 使用有意義的標籤名稱 &ndash; 建議您不要使用行話、標準或縮略字做為標籤名稱。請嘗試使用與使用者產生共鳴的名稱，以提高採用率。不是使用如 PII、PCI、HIPAA、LBI、MBI 和 HBI 這類的標籤，而是考慮如非商務、公用、一般、機密、高度機密這類的名稱。

### <a name="example-classification-schema"></a>分類結構描述範例

<table>
<thead>
<tr class="header">
<th align="left"><strong>標籤名稱</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">個人</td>
<td align="left">非商務資料，僅供個人使用。</td>
</tr>
<tr class="even">
<td align="left">公用</td>
<td align="left">特別準備並核准公開取用的商務資料。</td>
</tr>
<tr class="odd">
<td align="left">客戶資料</td>
<td align="left">包含個人識別資訊的商務資料。範例有信用卡號、銀行帳戶號碼和社會安全號碼。</td>
</tr>
<tr class="even">
<td align="left">HR 資料</td>
<td align="left">關於 Contoso 員工的人力資源資料，例如員工編號和薪資資料。</td>
</tr>
<tr class="odd">
<td align="left">機密</td>
<td align="left">若與未經授權的人員共用，可能對企業造成損害的敏感商務資料。範例包括合約、安全性報告、預測摘要和銷售帳單資料。</td>
</tr>
<tr class="even">
<td align="left">高度機密</td>
<td align="left">如果與未經授權的人員共用，將對企業造成損害的非常敏感商務資料。範例包括員工與客戶資訊、密碼、程式碼和預先公告的財務報表。</td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a>定義每一個標籤的分類與搜尋準則

在為您的組織開發分類結構描述之後，下一個步驟是開發用於尋找此資料的分類與搜尋準則。對於個人資料，您已經完成此工作，方法為識別敏感資訊類型，並為您的環境自訂或建立新的敏感資訊類型。

下表提供組織適用的結構描述、分類和搜尋準則範例。標籤依敏感性層級排序 (從最不敏感到最敏感) 以確保符合多個標籤條件的資料會被指派適當的標籤。

附註：提供的設定範例僅供說明，而不是做為部署指引和參考。

重點是確保您投入以針對 GDPR 規範分類個人資料的工作，與您整個組織的目標一致。

### <a name="example-schema-taxonomy-and-search-criteria"></a>結構描述、分類和搜尋準則範例

<table>
<thead>
<tr class="header">
<th align="left"><strong>標籤</strong></th>
<th align="left"><strong>分類</strong></th>
<th align="left"><strong>方法</strong></th>
<th align="left"><strong>搜尋語法</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">個人</td>
<td align="left">使用者手動標示為個人的文件。</td>
<td align="left">手動</td>
<td align="left">使用者手動標示為個人的文件。</td>
</tr>
<tr class="even">
<td align="left">公開</td>
<td align="left">包含不區分大小寫之字詞 Approved for Public Release ##/#### 的文件，其中 # 代表任何數字。</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Approved for Public Release*</p>
<p>RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">客戶資料</td>
<td align="left">歐盟公民資料的敏感資訊類型。</td>
<td align="left">敏感資訊類型</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">人力資源 — 員工資料</td>
<td align="left">以格式 CONTOSO-9##### 包含區分大小寫之員工 ID 的文件，其中 # 代表任何數字。</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — CONTOSO-9*</p>
<p>RegEx — (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">人力資源 — 薪資資料</td>
<td align="left">包含關鍵字 (不區分大小寫) Contoso AND 或關鍵字 (不區分大小寫) Salary OR Compensation 的文字</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso AND (Salary OR Compensation)</p>
<p>RegEx — (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="even">
<td align="left">機密</td>
<td align="left">包含字詞 (不區分大小寫) Contoso Confidential 的文件。</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso Confidential</p>
<p>RegEx — (?i)(\bContoso Confidential\b)</p></td>
</tr>
<tr class="odd">
<td align="left">高度機密</td>
<td align="left">包含字詞 (區分大小寫) Contoso Secret 或 Secret-C#### 的文件，其中 # 代表任何數字。</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso Secret OR Secret-C*</p>
<p>RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</p></td>
</tr>
</tbody>
</table>
