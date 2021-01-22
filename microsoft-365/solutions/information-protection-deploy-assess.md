---
title: 使用 Microsoft 365 評估資料隱私權風險並識別機密專案
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 判斷 Microsoft 365 環境中的資料隱私權法規、相關案例、您的準備以及敏感性資訊類型。
ms.openlocfilehash: c5a1662f5e82c8b8b9439439df0ee369d45e7616
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931899"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>使用 Microsoft 365 評估資料隱私權風險並識別機密專案

在實行任何相關改進動作之前，包括可與 Microsoft 365 功能和服務一起達成的動作，先評估貴組織所受之資料隱私權法規和風險是一項關鍵的第一步。 

## <a name="potentially-applicable-data-privacy-regulations"></a>可能適用的資料隱私權法規

若要瞭解更廣泛的資料隱私權法規架構，請參閱 [Microsoft 服務](https://servicetrust.microsoft.com/) 信任入口網站和一般資料保護規定 [ (GDPR) ](../compliance/gdpr.md)法規的系列文章，以及您產業或區域可能受規範之法規的其他資料。

### <a name="gdpr"></a>GDPR

GDPR 是資料隱私權法規中最知名且受到引用的法規，其規範與歐盟 (EU) 居民所識別或可識別的自然人有關之個人資料的收集、儲存、處理及共用。 

根據 GDPR 文章 4： 

- 個人資料是指與可識別之自然 (之資料主體之) ;可辨識的自然人是可直接或間接識別的人，特別是根據身分識別者，例如姓名、識別碼、位置資料、線上識別碼，或一或多個與該自然人實體、女性、心智、經濟、文化或社交身分有關的因素。

### <a name="iso-27001"></a>ISO 27001

支援 ISO 27001 等其他標準，也已被數個歐洲主管機關視為一種有效之人員、程式及技術範圍意圖的 Proxy。 其指定重迭和加入 ISO-27001 導向保護機制的標準可能會被視為在某些情況下符合部分隱私權義務的 Proxy。

### <a name="other-data-privacy-regulations"></a>其他資料隱私權法規

其他重要的資料隱私權法規也指定個人資料處理的需求。

在美國，包括加州消費者保護法 ([CCPA](../compliance/ccpa-faq.md)) 、HIPAA-HITECH (美國醫療保健隱私權法) 以及 Graham Leach Bliley Act (GLBA) 。 其他特定州/省/市法規也就地或開發中。 

在世界各地，其他範例包括德國的國家 GDPR 執行法案 (BDSG) 、巴西資料保護法 (<2> <4> <2>) PD 等等。

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>將規定與 Microsoft 365 技術控制類別進行比對

許多資料隱私權相關法規有重迭的需求，因此在開發任何技術控制方案之前，您應該先瞭解它們受哪些法規所規範。 

供本整體解決方案文章稍後參考，本表格提供資料隱私權法規樣本的摘要。 

| 調節 | 文章/區段 | 節錄 | 適用的技術控制項類別 |
|:-------|:-----|:-------|:-------|
| GDPR | 第 5 (1)  (f)  | 個人資料的處理方式應能確保個人資料的適當安全性，包括防範未經授權的或非法處理，以及使用適當的技術或組織措施 (，避免意外遺失、毀損或毀損。  |   (所有)  <br> 身分識別 <br> 裝置 <br> 威脅防護 <br> 保護資訊 <br> 規範資訊 <br> 探索和回應 |
|  | 本文 (32)  (1)  ()  | 在考慮到商業狀況、執行成本以及處理的性質、範圍、上下文和目的，以及自然人員的權利與自由之可能性和嚴重性等風險後，控制者與處理者應實施適當的技術和組織措施，以確保該風險的適當安全性層級，包括視需要相互攻擊： () 個人資料的假名和加密。 | 保護資訊 |
|  | 本文 (13)  (2)  ()  | "...控制者在取得個人資料時，應提供以下進一步資訊給資料主體，以確保合理且透明地處理： () 個人資料的儲存期限，或如果無法的話，則是用來決定該期間的準則。 | 規範資訊 |
|  | 文章 (15)  (1)  (e)  | 資料主體有權向控制者取得確認，確認是否正在處理有關他/她的個人資訊，以及在這種情況下，可存取個人資料和下列資訊： (e) 是否有要求控制者重新取得或清除個人資料的權利，或對於處理有關資料主體或針對此類處理物件之個人資料的處理限制 | 探索和回應 |
| <2> <2> <2> | 文章 46 | 處理代理人應採用安全性、技術及系統管理措施，以保護個人資料不受未經授權的存取，以及獲取、遺失、獲取、通訊，或任何類型的不當或非法處理之意外或非法狀況。 | 保護資訊 <br> 規範資訊 <br> 探索和回應|
|  | 文章 48 | 發生可能會對資料主體造成風險或相關損害之安全性事件時，控制者必須通知國家權力機關及資料主體。 | 探索和回應 |
| HIPPA-HITECH | 45 CFR 164.312 (e)  (1)  | 執行技術安全性措施，以防止未經授權的人員存取正以電子通訊網路傳輸的電子健康資訊。 | 保護資訊 |
|  | 45 C.F.R. 164.312 (e)  (2)  (ii)  | 在認為適當時，執行加密電子保護健康資訊的機制。 | 保護資訊 |
|  | 45 CFR 164.312 (c)  (2)  | 實用電子機制，確定電子受保護的健康資訊並未以未經授權的方式遭到更改或破壞。 | 規範資訊 |
|  | 45 CFR 164.316 (b)  (1)  (i)  | 如果此子部分要求記錄動作、活動或評定，請維護書面記錄 (這可能是電子) 、活動或評定的記錄 | 規範資訊 |
|  | 45 CFR 164.316 (b)  (1)  (ii)  | 將本節第 (b)  (1) 條要求的檔從建立日期或最後生效日期起保留 6 年，以較早之日期為准。 | 規範資訊 |
|  | 45 C.F.R. 164.308 ()  (1)  (ii)  (D)  | 執行程式以定期檢查資訊系統活動的記錄，例如稽核記錄、存取報告和安全性事件追蹤報告 | 探索和回應 |
|  | 45 C.F.R. 164.308 ()  (6)  (ii)  | 找出並回應可疑或已知的安全性事件;減輕所涵蓋實體或業務關聯者已知之安全性事件的可控制威脅;並記錄安全性事件及其結果。 | 探索和回應 |
|  | 45 C.F.R. 164.312 (b)  | 實制硬體、軟體和程式機制，記錄及檢查包含或使用電子保護健康資訊之資訊系統中的活動。 | 探索和回應 |
| CCPA | 1798.105 (c)  | 如果企業收到消費者的可驗證要求，要求刪除應細分的消費者個人資訊 (本節) 應刪除其記錄中的消費者個人資訊，並指示任何服務提供者從記錄中刪除該消費者的個人資訊 | 探索和回應 |
|  | 1798.105 (d)  |  (1798.105 的例外 (c)  <br> 如果企業或服務提供者必須維護消費者的個人資訊，以便維護消費者的個人資訊，企業或服務提供者就無需遵守消費者要求，以： (參照目前的法規以提供額外的資訊) 。 | 探索和回應 |
|||||

>[!Important]
>這不是完整的清單。 請參閱合規性 [管理員](../compliance/compliance-manager.md) 或您的法律或合規性顧問，進一步瞭解所引用章節是否可適用于列出的技術控制類別。
>

## <a name="knowing-your-data"></a>瞭解您的資料

無論您受哪些法規所規範，貴組織內外的不同使用者資料類型會與您的系統互動，都是可能會影響您整體個人資料保護原則的重要因素，但須遵守適用于貴組織的產業及政府法規。 這包括個人資料的儲存位置、資料類型、資料量，以及收集時的情況。
 
![瞭解您的資料：資料的類型、資料量，以及收集時的情況](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>資料可攜性 

資料也會在經過處理、調整及衍生的其他版本時，隨著時間而移動。 初始快照不夠用。 需要持續地瞭解您的資料。 對於處理大量個人資料的大型組織來說，這是其中一項最大的挑戰。 不解決「知道您的資料」問題的組織，其風險可能相當高，而且可能會由監管單位進行微調。

![資料生命週期](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>個人資料位於何處

若要解決資料隱私權法規，您不論目前或未來，都別想依賴一般概念來表示個人資料可能存在於何處。 資料隱私權法規要求組織持續瞭解個人資料的提供位置。 因此，為包括您的 Microsoft 365 環境在內的個人資訊儲存，一併建立持續監控與偵測的機制，對於您所有資料來源的初始快照非常重要。

如果您尚未評估與資料隱私權法規相關的整體整備狀況和風險，請使用下列三步驟架構來開始使用。 

![評估您整體整備情況與資料隱私權法規相關之風險的步驟](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>本文及其內容不能代表法律諮詢服務。 它只提供一些基本的指引和連結，以連結到在評估的初期可能提供協助的工具。
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>步驟 1：建立組織個人資料案例的基礎理解 

您需要根據目前所管理之個人資料的類型、資料的儲存位置、對資料進行哪些保護控制、系統生命週期的管理方式，以及誰可以存取資料，來判斷資料隱私權風險曝光率。 

從起點來說，清點 Microsoft 365 環境中存在哪些類型的個人資料是很重要的。 使用這些類別：

- 執行日常業務功能所需的員工資料
- 組織擁有有關其商務客戶、合作夥伴，以及企業對企業的其他 (B2B) 案例
- 組織有關于消費者的資料，它們提供資訊給組織在企業對客戶服務情況下所管理的線上服務 (B2C) 案例

以下是組織中一般部門之不同資料類型的範例。

![個人資料類型](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

許多受資料隱私權規定保護的個人資訊通常是收集並儲存在 Microsoft 365 之外。 針對消費者的 Web 或行動應用程式的任何個人資料，必須從這類應用程式匯出至 Microsoft 365，才能受到 Microsoft 365 內資料隱私權審核的檢查。 

相對於您的 Web 應用程式和 CRM 系統而言，Microsoft 365 的資料隱私權公開可能會受到限制，此解決方案無法解決這些限制。

評估您的風險設定檔時，也考慮下列常見的資料隱私權合規性挑戰：

 - **個人資料發佈。** 關於給定主題的資訊散佈程度如何？ 向監管機構指出已實施適當控制措施，是已知的嗎？ 需要時，可以進行調查和修復嗎？
- **防止外泄。** 如何保護所提供類型或來源的個人資訊不受入侵，以及如何回應？
- **保護與風險。** 哪些資訊保護機制適用于風險，以及如何在需要使用者介入時維持業務持續性和生產力，並儘量降低使用者的影響？ 例如，應該使用手動分類或加密嗎？
- **個人資料保留。** 基於有效的商務理由，包含個人資料的資訊需要保留多久時間，以及如何避免過去的永續保留做法，並滿足保留對於業務持續性的需求？
- **處理資料主體要求。** 需要哪些機制來處理 DSR (資料主體要求) 匿名、重新處理和刪除等任何補救動作？
- **持續監視及報告。** 不同的資料類型和來源可以使用哪些日常監視、報告方法及報告技術？
- **資料管理的限制。** 對於透過這些方法收集或儲存的資訊，組織在隱私權控制中必須反映的資料使用是否有限制？ 例如，銷售人員不會使用個人資料的承諾可能會要求貴組織建立機制，防止資訊轉移或儲存至與銷售組織相關的系統中。

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>執行日常業務功能所需的員工資料

根據組織在員工同意之條款中的意見，組織自然需要收集員工資料，以用於電子身分識別及人力資源用途。 只要某人為公司工作，通常這不是問題。 組織可能想要建立機制，防止惡意執行者將員工個人資料外泄或外泄。 

如果有人離職，組織通常會有移除使用者帳戶、解除授權信箱和個人磁片磁碟機，以及變更人力資源系統等專案之員工狀態的程式、程式，以及保留與刪除排程。 在涉及訴訟的情況下，進行法律調查的員工或其他方可能擁有取得儲存在組織系統中之個人資料之相關資訊的有效理由。 在某些情況下，該方可能會要求移除或匿名提供這些資料。 

為滿足這類需求，組織應就地處理預防、預防及補救需求的程式，以協助這類要求，同時指出員工某些相關資訊可合理被視為對於業務持續性至關重要。 例如，個別作者撰寫檔案或執行函數的資訊。 

>[!Note]
>有關 Microsoft 365 中個人資料的補救和補救技術，請參閱 [監控和回應文章](information-protection-deploy-monitor-respond.md)。 您可能也想要採用自動化分類和保護設定，以確保個人資料在組織內部受到控制，以及避免資料在惡意執行者情況下離開組織。 詳細資訊 [請參閱保護](information-protection-deploy-protect-information.md) 資訊文章。
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>組織在 B2B 分析情境中擁有關于其商務客戶的資料

B2B 資訊的收集也是一項挑戰，因為貴組織可能需要保留其各種系統中客戶名稱和交易的記錄，以用於商業持續性用途，同時保護該資訊不受意外或惡意的外泄。 與員工資料一樣，組織必須實施政策、程式及技術控制，以保護這類資料，以及根據定義的保留和刪除排程來保留資料。 

一般來說，與外部客戶、合作夥伴及與組織有業務往來的其他實體所簽訂合約，在實體與組織建立關係期間與之後，會以語言來處理這類資料的處理方式，包括保護、保留和刪除。 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>組織對於提供資訊給組織在 B2C 情境中管理之線上服務的消費者資料

因為客戶資料洩漏的眾多公開實例，此類別是大多數使用者會考慮的資料隱私權。 此行為可能是刻意的，例如與提供者簽約的協力廠商，或是不小心的，例如惡意執行者將內容縮至。 消費者資料保護是歐盟及其他國家對於這些法規最理由之一。 GDPR 和 CCPA 等資料隱私權法規會要求您針對：

- [行動計畫與](../compliance/gdpr-action-plan.md)[責任檢查清單](../compliance/gdpr-arc-office365.md)
- [資料保護影響評定](../compliance/gdpr-data-protection-impact-assessments.md)
- [外泄通知](../compliance/gdpr-breach-office365.md)
- [資料主體要求](../compliance/gdpr-dsr-office365.md)

如果貴組織並未執行許多直接來自消費者的資料收集，則此類別可能比較不會是問題。 不過，您仍可能需要執行這些文章中所述的程式，才能達成合規性。

### <a name="step-1-summary"></a>步驟 1 摘要

根據組織個人資料案例的基礎，瞭解您的風險曝光和資料隱私權規定是一個重要的第一步。

如果您的 Microsoft 365 環境中沒有消費者提供的個人資訊，或者資料受限於環境的某些部分，而需要進行技術支援時，需進行消費者型資料曝光，那麼該技術支援可能只需要用於環境高風險部分，而非所有地區。

雖然外部組織或標準控制集建議 ，例如來自 Microsoft 365 的合規性管理員建議可協助瞭解您的控制策略，但您的實作選擇應該要以資料庫存認知為導向，以量化您的實際風險曝光。

大部分的組織都會受到上述其中一種案例的曝光。 對評估採取全盤考慮非常重要。

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>步驟 2：評估您遵守資料隱私權法規的準備情況

雖然 GDPR 是特定的問題，但免費 [Microsoft GDPR](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) 評定工具中提出問題，可為您提供瞭解整體資料隱私權整備情況的好起點。 

受到其他資料隱私權法規保護的組織 ，例如美國的 CCPA 或巴西的CCPD，可能也會受益于此工具中對 GDPR 的因應重迭規定所提供之準備的庫存。

GDPR 評定由以下各節組成：

| 區段 | 說明 |
|:-------|:-----|
| 控管 | <ol><li>您的隱私權原則是否明確說明正在處理哪些資料資訊？ </li><li>您是否定期在 PIAs 中執行隱私權影響 (評定) ？ </li><li> 您是否使用工具來管理 PI 或 PI () ？ </li><li> 您是否具有法律授權，可針對任何一項個人使用 PI 資料進行業務？ 您是否會追蹤資料的同意？ </li><li> 您是否要追蹤、執行及管理稽核控制措施？ 您是否要監控資料外泄？ </li></ol>|
| 刪除和通知 | <ol><li>您是否提供可存取使用者資料之明確指示？ </li><li> 您是否已記錄處理退出宣告同意的已記錄程式？ </li><li> 您是否有資料的自動化刪除程式？ </li><li>   與客戶互動時，您是否有驗證身分識別的驗證程式？ </li></ol>|
| 風險降低與資訊安全性 | <ol><li>您是否使用工具來掃描非結構化資料？ </li><li>所有伺服器是否都是最新的，而且您是否利用防火牆來保護它們？ </li><li>您是否定期備份伺服器？ </li><li>您是否主動監視資料外泄？ </li><li>您是否在休息和傳輸中加密您的資料？ </li></ol>|
| 原則管理 | <ol><li>如何管理與 BCRs 或 BCR (公司規則) ？ </li><li>您是否會追蹤資料的同意？ </li><li> 以 1 到 5、5 為完全涵蓋的縮放比例，您的合約是否涵蓋資料分類和處理需求？ </li><li>您是否已擁有並定期測試事件回應計畫？ </li><li>您用什麼政策來管理存取權？ </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>步驟 3：找出 Microsoft 365 環境中發生的敏感性資訊類型。 

此步驟涉及識別受到特定法規管控的特定敏感性資訊類型，以及這些類型在 Microsoft 365 環境中出現的情況。 

在環境中尋找包含個人的內容可能會是一項困難的工作，之前會涉及使用合規性搜尋、電子檔探索、進版電子檔探索、DLP 和稽核的組合。 

有了 Microsoft合規性系統管理中心內建的資料分類解決方案，使用內建或自訂的[](../compliance/data-classification-content-explorer.md)敏感性資訊類型 ，包括與個人資料相關的內容 Explorer 功能，這項功能變得更容易了。
 
### <a name="sensitive-information-types"></a>敏感性資訊類型

Microsoft 合規性系統管理中心會預先載入超過 100 種敏感性資訊類型，大部分與識別及尋找個人資料有關。 根據正則運算式 (RegEx) 或函數所定義的模式，這些內建的敏感性資訊類型可協助識別及保護信用卡號碼、銀行帳戶號碼、護照號碼等。 若要深入了解，請參閱[機密資訊類型尋找的目標為何](../compliance/what-the-sensitive-information-types-look-for.md)。

如果您需要識別及保護特定組織或區域機密專案類型 ，例如員工標識的自訂格式，或內建敏感性資訊類型未涵蓋的其他個人資訊，您可以使用這些方法建立自訂的敏感性資訊類型： 

- PowerShell
- 資料完全相符的自訂規則 (EDM) 
- 透過合規性中心系統管理 UI，如使用合規性分數和合規性管理員 [文章中的強調顯示](information-protection-deploy-compliance.md)

您也可以自訂現有的內建敏感性資訊類型。

請參閱以下文章以進一步查看：

- [自訂內建的敏感性資訊類型](../compliance/customize-a-built-in-sensitive-information-type.md)
- [瞭解敏感性資訊類型](../compliance/sensitive-information-type-learn-about.md)
- [在安全性與合規性中心建立自訂敏感性資訊類型](../compliance/create-a-custom-sensitive-information-type.md)
- [在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>內容瀏覽器

Microsoft 365 合規性系統管理中心的新內容管是決定環境中[](../compliance/data-classification-content-explorer.md)敏感性專案出現的重要工具。 這是一種自動化工具，可針對敏感性資訊類型出現和顯示結果，進行初始和持續掃描整個 Microsoft 365 訂閱。
 
新的內容管理器工具可讓您使用內建的敏感性資訊類型或自訂類型，快速識別您環境中機密專案的位置。 這可能包括建立程式並指派職責，定期調查機密專案的目前狀態和位置。

除了本文中強調說明的其他步驟外，本文還提供一個起點，以便透過規劃的 Microsoft 365 組配置及監控，識別您的整體風險曝光、整備狀況，以及要保護之機密專案的位置。 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>識別您環境中個人資料的其他方法

除了內容瀏覽器之外，組織還能夠存取內容搜尋功能，以使用進位搜尋準則和自訂篩選來產生自訂搜尋，以尋找其環境中的個人資訊。

本文提供使用內容搜尋來探索個人資料的詳細 [指引](../compliance/search-for-and-find-personal-data.md)。 GDPR 和 CCPA 的 [DSR](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs)也會探索內容搜尋和其他探索技術。

Microsoft 365 中個人資料的其他深入資訊及補救技術，會于監控和回應 [文章中提供](information-protection-deploy-monitor-respond.md)。
