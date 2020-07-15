---
title: 將標籤套用至個人資料
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何使用 Office 標籤做為一般資料保護規定 (GDPR) 保護計劃的一部分。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126814"
---
# <a name="apply-labels-to-personal-data"></a>將標籤套用至個人資料

 如果您使用分類標籤做為 GDPR 保護計劃的一部分，請使用本主題。 

如果您使用標籤來保護 Microsoft 365 中的個人資料，Microsoft 建議從使用[保留標籤](retention.md#retention-labels)開始。 使用保留標籤，您可以：
- 使用「進階資料控管」，根據敏感性資訊類型或其他準則自動套用標籤。
- 使用保留標籤搭配資料外洩防護來套用保護。 
- 使用標籤搭配電子文件探索和內容搜尋。 

雲端 App 安全性目前不支援保留標籤，但是您可以使用 Microsoft 365 敏感資訊類型搭配雲端 App 安全性，監視位於其他 SaaS 應用程式中的個人資料。

目前建議使用[敏感度標籤](sensitivity-labels.md)，將標籤套用至內部部署與其他雲端服務和提供者中的檔案。 也有對於 Microsoft 365 中需要使用 Azure 資訊保護加密進行資料保護的檔案 (例如商業秘密檔案) 所建議的事項。

目前，對於 Microsoft 365 中具有、受限於 GDPR 資料的檔案，不建議使用 Azure 資訊保護來套用加密。 Microsoft 365 服務目前無法讀取使用 AIP 加密的檔案。 因此，服務找不到這些檔案中的敏感資料。

您可對 Exchange Online 中的郵件套用保留標籤，而這些標籤可搭配 Microsoft 365 資料外洩防護使用。 

![Microsoft 365 標籤和 Azure 資訊保護標籤](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


在此圖例中：

-   將保留標籤用於個人資料，以及 SharePoint Online 和商務用 OneDrive 中高度管制的商業機密檔案。
-   Microsoft 365 敏感資訊類型可以用於 Microsoft 365 之中，也可以搭配雲端 App 安全性，監視位於其他 SaaS 應用程式中的個人資料。
-   將敏感度標籤用於高度管制的商業機密檔案、Exchange Online 電子郵件、其他 SaaS 服務中的檔案、內部部署資料中心中的檔案，以及其他雲端提供者中的檔案。


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>在 Microsoft 365 間使用保留標籤和敏感性資訊類型以保護資訊

下圖顯示如何在標籤原則、資料外洩防護原則，以及搭配雲端 App 安全性原則使用保留標籤和敏感性資訊類型。

![Office 標籤和敏感資訊類型](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

為了便於存取，下表會在圖例中提供相同的範例。

<table>
<thead>
<tr class="header">
<th align="left"><strong>分類元素</strong></th>
<th align="left"><strong>標籤原則 — 2 個範例</strong></th>
<th align="left"><strong>資料外洩防護原則 — 2 個範例</strong></th>
<th align="left"><strong>所有 SaaS 應用程式的雲端 App 安全性原則 — 1 個範例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">保留標籤。 範例：個人、公用、客戶資料、HR 資料、機密、高度機密</td>
<td align="left"><p>Auto apply this label . . .</p>
<p>客戶資料</p>
<p>. . . to documents that match these sensitive information types . . .</p>
<p>&lt;敏感資訊類型範例的清單&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;定義保護&gt;</p>
<p>. . . to documents with this label . . .</p>
<p>客戶資料</p></td>
<td align="left"><p>Alert when files with these attributes . . .</p>
<p>選擇一或多個屬性：預先定義的 PII 屬性、Microsoft 365 敏感資訊類型、敏感度標籤 (AIP)、自訂運算式</p>
<p>。 。 。 在組織外共用時發出警示</p><p>附註：雲端 App 安全性目前不支援保留標籤。</td>
</tr>
<tr class="even">
<td align="left">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</td>
<td align="left"><p>Publish these labels for users to manually apply . . .</p>
<p>&lt;選取標籤&gt;</p>
<p>. . . to these locations . . .</p>
<p>&lt;所有位置或選擇特定位置&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;定義保護&gt;</p>
<p>. . . to documents that match these sensitive information types&gt;</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>指定自動套用標籤原則的優先順序

For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.

The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it's important to carefully plan the roll-out. Here's what you need to know.

### <a name="one-label-at-a-time"></a>一次一個標籤

您只能將一個標籤指派給一個文件。

### <a name="older-auto-apply-policies-win"></a>越舊的自動套用原則越優先採用

If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it's important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>手動使用者套用標籤優先於自動套用標籤

Manual user applied labels trump auto-applied labels. Auto-apply policies can't replace a label that is already applied by a user. Users can replace labels that are auto-applied.

### <a name="auto-assigned-labels-can-be-updated"></a>可以更新自動指派的標籤

更新的標籤原則或現有原則的更新，可以更新自動指派的標籤。

請確定實作標籤的計劃包括：

- 指定建立自動套用原則的優先順序。

- Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>建立自動套用原則的優先順序範例

<table>
<thead>
<tr class="header">
<th align="left"><strong>標籤</strong></th>
<th align="left"><strong>建立自動套用原則的優先順序</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">人力資源 — 員工資料</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">客戶資料</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">高度機密</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">人力資源 — 薪資資料</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">機密</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">公開</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">個人</td>
<td align="left">沒有自動套用原則</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>建立標籤和自動套用標籤原則

在安全性中心或合規性中心中建立標籤和原則。

<table>
<thead>
<tr class="header">
<th align="left"><strong>步驟</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將權限授與規範小組的成員。</p></td>
<td align="left"><p>Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</p>
<p>請參閱<a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">讓使用者能夠存取安全性中心和/或合規性中心</a>。</p></td>
</tr>
<tr class="even">
<td align="left"><p>建立保留標籤。</p></td>
<td align="left">移至安全性中心或合規性中心中的 [分類]，選擇 [保留] 標籤，然後建立適用於您環境的標籤。</td>
</tr>
<tr class="odd">
<td align="left"><p>建立標籤的自動套用原則。</p></td>
<td align="left">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</td>
</tr>
</tbody>
</table>

下圖顯示如何為客戶資料標籤建立自動套用標籤。

![為客戶資料建立及套用標籤](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

在此圖例中：

- 已建立「客戶資料」標籤。

- 已列出所需的敏感資訊類型範例：比利時國民編碼、信用卡號碼、克羅埃西亞身分證號碼、芬蘭國民身分證

- 建立自動套用原則可將標籤「客戶資料」指派給任何檔案，其中包含您新增至原則的其中一個敏感資訊類型。
