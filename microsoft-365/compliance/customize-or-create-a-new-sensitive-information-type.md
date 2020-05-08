---
title: 自訂或建立新的敏感資訊類型
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
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
ms.custom: seo-marvel-apr2020
ms.assetid: ''
description: 了解如何為一般資料保護規定 (GDPR) 修改或建立新的 Office 365 敏感資訊類型。
ms.openlocfilehash: 3eca04fcf949a19615dc574c90d8dbeea0894a23
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166064"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a>自訂或建立新的敏感資訊類型

本文提供三個範例，示範如何為 GDPR 修改或建立新敏感資訊類型。

- 修改現有的敏感資訊類型 — 歐盟轉帳卡卡號

- 建立新的敏感資訊類型 — 電子郵件地址

- 利用 XML 檔案範例建立新的敏感資訊類型 — Contoso 客戶編號

另請參閱：

- [使用 PowerShell 建立自訂的敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [自訂內建的敏感性資訊類型](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a>修改敏感資訊類型以提高精確度

如果您使用的是內容搜尋，以利用敏感資訊類型搜尋個人資訊，而且並未傳回預期的結果，或查詢傳回太多誤判，請考慮修改敏感資訊類型，以更有效地使用您的環境。

建立或自訂敏感資訊類型的最佳做法是根據現有的敏感資訊類型建立新的敏感資訊類型，同時為它提供唯一名稱和識別碼。比方說，如果您想要調整「歐盟轉帳卡卡號」敏感資訊類型的參數，您可以將該規則的複本命名為「歐盟轉帳卡加強版」，以與正本區別。

在新的敏感資訊類型中，只需修改您想要變更以提高其精確度的值。一旦完成，就上傳新的敏感資訊類型，並建立新的 DLP 規則 (或修改現有的 DLP 規則)，來使用您剛新增的敏感資訊類型。修改敏感資訊類型的精確度需要反復試驗，所有保留原始類型的複本可讓您在未來需要時回到最初狀態。

若要自訂敏感資訊類型：

1.  匯出 Office 365 中內建的敏感資訊類型的現有 Microsoft 規則套件。

2.  重新命名此 XML 檔案，並在您最愛的 XML 編輯器中開啟。

3.  隔離敏感資訊類型，並移除所有其他敏感資訊類型。

4.  使用 PowerShell 為您正在修改的敏感資訊類型產生兩個新的 GUID。

5.  修改識別碼和其他基本元素，讓敏感資訊類型成為唯一的 (這包括將兩個 GUID 取代為您產生的新 GUID)。

6.  調整比對需求以改善精確度。

    1.  鄰近修改 — 修改字元模式鄰近，以展開或縮小必須在其中根據敏感資訊類型尋找關鍵字的視窗。

    2.  關鍵字修改 — 將關鍵字新增至其中一個 \<Keywords\> 元素，提供我們的敏感資訊類型更特定的補強證據，以便表示根據此規則進行比對。或是，移除將造成誤判的關鍵字。

    3.  信賴度修改 — 修改敏感資訊類型必須符合其定義中指定之準則，然後才能發出並報告相符項目的信賴度。

7.  上傳新的敏感資訊類型。

8.  重新編目內容以識別敏感資訊。請參閱[手動要求重新編目網站和重新編製網站檢索](https://docs.microsoft.com/sharepoint/crawl-site-content)。

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a>範例：修改「歐盟轉帳卡卡號」敏感資訊類型。

在任何系統中改善 DLP 規則的精準度，需要測試範例資料集，而且可能需要反復修改和測試以進行微調。本範例示範如何修改「歐盟轉帳卡卡號」敏感資訊類型來改善其精確度。

在我們的範例中搜尋歐盟轉帳卡卡號時，該卡號的定義會使用複雜模式嚴格定義為 16 位數，並取決於總和檢查碼的驗證。由於此敏感資訊類型的字串定義，我們無法變更此模式。不過，我們可以進行下列調整，以改善 DLP 在 Office 365 內尋找敏感資訊類型的精確度。

### <a name="proximity-modification"></a>鄰近修改

我們將縮小視窗，方法為將 \<Entity\> 元素中的 patternProximity 值從 300 個字元修改為 150 個字元。這表示我們的補強證據或關鍵字必須更接近敏感資訊類型，才能表示根據此規則進行比對。

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

### <a name="keyword-modifications"></a>關鍵字修改

某些關鍵字可能會導致誤判。因而，您可能想要移除關鍵字。以下是這個範例的關鍵字：

\<Keyword id="Keyword\_card\_terms\_dict"\>

\<Group\>

\<Term\>corporate card\</Term\>

\<Term\>organization card\</Term\>

\<Term\>acct nbr\</Term\>

\<Term\>acct num\</Term\>

\<Term\>acct no\</Term\>

…

\</Group\>

\</Keyword\>

### <a name="confidence-modifications"></a>信賴度修改

如果從定義中移除關鍵字，則您通常想要降低此值，調整您對找到此敏感資訊類型的信賴度。歐盟轉帳卡卡號類型的預設層級是 85。

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

…

\</Pattern\>

\</Entity\>

## <a name="create-a-new-custom-sensitive-information-type"></a>建立新的自訂敏感資訊類型

若要建立新的自訂敏感資訊類型，請先使用內容搜尋：

-   最佳化 KQL 查詢

-   查看哪些關鍵字最有用

使用這些結果來建立新的敏感資訊類型。然後，為您的環境最佳化新的敏感資訊類型。

附註： 對於歐盟國家中的個人資料，即將推出許多新的敏感資訊類型。如果您需要建立新的敏感資訊類型，請先對準您環境的自訂資料。

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a>步驟 1 — 使用 KQL 查詢和關鍵字，在您的環境中尋找額外資料

您可能需要建立額外的查詢，以尋找受到 GDPR 約束的個人資料。內容搜尋會使用關鍵字查詢語言 (KQL) 來尋找資料。若沒有敏感資訊類型，無法只使用 KQL，精確地偵測到最敏感的資料。因此，目標是使用內容搜尋來測試和最佳化 KQL 字串，然後使用這些以建立並調整新的敏感資訊類型，在這裡您甚至可以達到更高的精確度。

使用下列資源，利用 KQL 來制訂和最佳化查詢：

- [關鍵字查詢語言 (KQL) 語法參考 (DMC)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [執行內容搜尋](content-search.md)

內容搜尋提供另一種資源，協助您開發 KQL 查詢及敏感資訊類型 — 關鍵字。為什麼使用關鍵字清單？您可以取得統計資料，顯示多少個項目比對每一個關鍵字的。這可協助您快速識別哪些關鍵字的效率最好 (最差)。如需搜尋統計資料的詳細資訊，請參閱[檢視內容搜尋結果的關鍵字統計資料](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search)。

每一列上的關鍵字是藉由所建立的搜尋查詢中的 OR 運算子來連線。您也可以連續使用關鍵字片語 (以括號括住)。

如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)。

### <a name="exampleusing-content-search-to-identify-email-addresses"></a>範例 — 使用內容搜尋來識別電子郵件地址

電子郵件地址會被視為與資料主旨相關的敏感資訊。這是一個簡單範例，示範如何協助內容搜尋。

無法同時使用 KQL 和關鍵字。分別使用這些工具來調整您的查詢，並判斷可能有助於敏感資訊類型的關鍵字。

### <a name="kql-query"></a>KQL 查詢

(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)

附註：

-   您可以使用 NEAR 和 ONEAR 進行鄰近搜尋。

-   很遺憾，KQL 不支援具有 Regex 類別的查詢 (例如：IdRef="Regex\_email\_address")

### <a name="keywords"></a>關鍵字

在個別行中輸入每一個關鍵字。範例關鍵字：

-   email address

-   mail

-   contact

-   sender

-   recipient

-   cc

-   bcc

在此範例中，您可能了解關鍵字不是必要的，並產生許多誤判結果。

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a>步驟 2 — 建立新的自訂敏感資訊類型

在使用 KQL 查詢和關鍵字來識別敏感資訊之後，請使用這些來建立新的自訂敏感資訊類型。在許多情況下，您將需要精密的敏感資訊類型，才能達到正確的精確層級。然後，您可以在 DLP 原則和其他工具中，以及在其他 KQL 查詢內，使用這些自訂的敏感資訊類型與內容搜尋搭配。

最佳做法是根據現有的敏感資訊類型建立新的敏感資訊類型。請使用本文稍早所述的相同程序。

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a>範例 — 為電子郵件地址建立新的敏感資訊類型 

我們將繼續使用電子郵件地址做為範例，因為它使用簡單。下表詳述針對新電子郵件敏感資訊類型的修改建議。

<table>
<thead>
<tr class="header">
<th align="left"><strong>步驟</strong></th>
<th align="left"><strong>修改</strong></th>
<th align="left"><strong>XML 語法範例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">設定 IdRef 屬性
<p>在 &lt;Entity&gt; 元素內，修改 &lt;IdMatch&gt; 元素，以便將 idRef 屬性 = 唯一值。此值將指向定義規則運算式以尋找電子郵件地址的元素。</p></td>
<td align="left">IdRef=&quot;Regex_email_address&quot;</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left"><p>Proximity 屬性</p>
<p>在 &lt;Entity&gt; 元素中，patternProximity 的值將從 300 開始。</p></td>
<td align="left">patternsProximity=&quot;300&quot;</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left"><p>信賴等級</p>
<p>將 recommendedConfidence 屬性設為您覺得有信心找到確切相符項目的值。這可能需要利用具有代表性的資料集進行測試，以取得精確結果。請將此值設為 75，做為初始設定。</p></td>
<td align="left"><p>recommendedConfidence=&quot;75&quot;&gt;</p>
<p>前三個項目合併所產生的 XML 如下所示：</p>
<p>&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</p>
<p>&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</p>
<p>&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</p>
<p>&lt;Any minMatches=&quot;1&quot;&gt;</p>
<p>&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</p>
<p>&lt;/Any&gt;</p>
<p>&lt;/Pattern&gt;</p>
<p>&lt;/Entity&gt;</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left"><p>Regex 元素</p>
<p>在 &lt;Entity&gt; 元素下方立即新增 &lt;Regex&gt; 元素，其會定義用來識別電子郵件地址的規則運算式。</p></td>
<td align="left">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left"><p>關鍵字</p>
<p>在 &lt;Regex&gt; 元素下方新增 &lt;Keyword&gt; 元素，其會定義電子郵件相關之關鍵字的清單。請確保 &lt;Keyword&gt; 元素的 id 值符合 &lt;Entity&gt;&lt;Pattern&gt;元素中的 &lt;Match idRef&gt; 值。必要時，您可以繼續新增自己的關鍵字。</p>
<p>關鍵字不一定包含在電子郵件的機密資訊類型中。我們提供下列關鍵字做為範例。</p></td>
<td align="left"><p>&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</p>
<p>&lt;Group&gt;</p>
<p>&lt;Term&gt;email&lt;/Term&gt;</p>
<p>&lt;Term&gt;email address&lt;/Term&gt;</p>
<p>&lt;Term&gt;contact&lt;/Term&gt;</p>
<p>&lt;/Group&gt;</p>
<p>&lt;/Keyword&gt;</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left"><p>LocalizedStrings 元素</p>
<p>在 &lt;LocalizedStrings&gt;&lt;Resource&gt; 元素中，確認您有唯一名稱，可識別敏感資訊類型。</p></td>
<td align="left"><p>&lt;LocalizedStrings&gt;</p>
<p>&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</p>
<p>&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</p>
<p>&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</p>
<p>&lt;/Resource&gt;</p>
<p>&lt;/LocalizedStrings&gt;</p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a>利用 PowerShell 和 XML 檔案範例建立新的敏感資訊類型 — Contoso 客戶編號

Contoso 使用 Contoso 客戶編號 (CCN) 來識別其客戶資料庫中的每一個客戶。CCN 由下列分類法組成：

-   兩位數，代表建立記錄的年份。Contoso 成立於 2002。因此，最早的可能值是 02。

-   三位數，代表建立記錄的夥伴機構。可能的機構值範圍從 000 到 999。

-   一個字母字元，代表行業。可能值為 a 到 z，而且應該不區分大小寫。

-   一個四位數序號。可能的序號值範圍從 0000 到 9999。

CCN 範例：

> 15080P9562
>
> 14040O1119
>
> 15020J8317
>
> 14050E2330
>
> 16050E2166
>
> 17040O1118

Contoso 一律在內部通信、外部通信、文件等使用 CCN 來表示客戶。他們想要建立自訂的敏感資訊類型，來偵測 CCN 的使用情形，以便可在使用此形式的個人資料時套用保護。

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a>為 Contoso 客戶編號建立新的敏感資訊類型

<table>
<thead>
<tr class="header">
<th align="left"><strong>步驟</strong></th>
<th align="left"><strong>動作</strong></th>
<th align="left"><strong>結果</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Contoso 使用 PowerShell 和內容搜尋，來尋找符合 CCN 範例集的文件。</td>
<td align="left">

<p>#連線到安全性與合規性中心</p>
<p>$adminUser = &quot;alland@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#建立並開始搜尋範例資料</p>
<p>$searchName = &quot;Sample Customer Information Search&quot;</p>
<p>$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</p>
<p>New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</p>
<p>Start-ComplianceSearch -Identity $searchName</p>
</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Contoso 分析結果。每次使用 CCN，就會使用歐盟格式的日期，也會在鄰近的 300 個字元內使用這些關鍵字的其中一個。</td>
<td align="left">customer number、customer no、customer #、customer#、Contoso customer</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Contoso 已開發下列規則運算式 (RegEx) 模式來識別其 CCN。</td>
<td align="left">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">Contoso 已開發下列規則運算式 (RegEx) 模式，以其各個子公司所使用的格式識別歐盟日期。</td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">Contoso 使用 PowerShell 來產生三個唯一的 GUID。</td>
<td align="left"><p>#為 RulePack Id、Publisher Id 及 Entity Id 產生唯一的 GUID</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left">Contoso 為其敏感資訊類型規則定義下列參數。</td>
<td align="left"><p>名稱：Contoso 客戶編號 (CCN)</p>
<p>描述：尋找其他關鍵字和歐盟格式日期的 Contoso 客戶編號 (CCN)</p></td>
</tr>
<tr class="odd">
<td align="left">7</td>
<td align="left">Contoso 為新的敏感資訊類型建立 XML 檔案，以偵測 Contoso 客戶編號 (CCN)，並使用 UTF-8 編碼方式，在本機檔案系統將此值儲存為 C:\Scripts\ContosoCCN.xml。</td>
<td align="left">請參閱本表下方的 XML 檔案。</td>
</tr>
<tr class="even">
<td align="left">8</td>
<td align="left">Contoso 使用下列 PowerShell 建立自訂的敏感資訊類型。</td>
<td align="left"><p>#連線到安全性與合規性中心</p>
<p>$adminUser = &quot;alland@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#建立新的敏感資訊類型。</p>
<p>New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a>新的敏感資訊類型的 XML 檔案範例 (步驟 7)
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
