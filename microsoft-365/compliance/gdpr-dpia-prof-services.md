---
title: 使用 Microsoft 專業服務的資料控制站的指導
description: 本文件提供資訊可協助他們決定是否需要 DPIA Professional 服務和功能包含詳細說明資料控制的站。
keywords: DPIA、 Microsoft 專業服務、 Microsoft 365 文件 GDPR
robots: NOINDEX,NOFOLLOW
author: BrendaCarter
ms.localizationpriority: high
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 9e710c3b8ec0c467c36a675c2d76eabb3af1f0f6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866376"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-professional-services"></a>使用 Microsoft 專業服務的資料控制站的資料保護影響評估： 指引

## <a name="introduction-to-microsoft-professional-services"></a>Microsoft 專業服務簡介

Microsoft 專業服務包括各種群組設為多並獲得更多的技術架構師、 工程師、 顧問、 及專用於傳遞的賦予客戶在 Microsoft 的任務上支援專業人員。此處了解更多關於 Microsoft 專業服務 (<https://www.microsoft.com/microsoftservices/professional_services.aspx>) 及 Microsoft 信任中心上移至 [Microsoft 專業服務] 區段中 (<https://www.microsoft.com/trustcenter/cloudservices/commercialsupport>)。

Microsoft 專業服務嚴重採用其責任下一般資料保護法規 (GDPR)。這份文件中的資訊設計來提供資訊 Microsoft 的支援和諮詢客戶時可以使用準備的資料保護影響評估 (DPIAs) GDPR 底下的方案。

### <a name="introduction-to-dpias"></a>DPIAs 簡介

一般資料保護法規 (GDPR)、 資料控制器所需準備 DPIA 處理的作業中為"有可能導致高風險的權限和的自然人員 freedoms。 」沒有固有一定會需要 DPIA 建立所使用的資料控制站的 Microsoft 專業服務中。而是 DPIA 是否需要將會取決於詳細資料與內容類型的服務和資料控制器使用專業服務的方式。

本文件的用途是提供專業人員的相關服務資訊可協助他們決定是否需要 DPIA 和若是如此，項目詳細資料包含資料控制站。

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>第 1 部分 – 判斷是否需要 DPIA

本文 35 GDPR 需要建立的資料保護影響評估"[w] 以下一種特別處理使用新的技術及考慮事項性質、 範圍、 內容及處理的目的是可能造成的資料控制站在高風險的權限和的自然人員 freedoms。 」將進一步設定出特定會指出這類高風險的因素下表中所討論。在決定是否需要 DPIA、 資料控制器應考慮這些因素，以及其他相關因素根據資料控制站的特定實作與 use(s) 的專業服務。

***表 1-風險因素及相關資訊***

<!--start table here NO HEADER -->

|||
|:-----|:-----|
|**風險因素**|**專業服務的相關資訊**|
|基於自動化處理對自然人的個人方面進行系統和廣泛的評估，包括概況分析，以及對自然人產生法律效果的決定或對自然人產生同樣重大影響的決定；|專業服務並未執行某些常式或自動化的資料處理，例如符號修正支援 （例如，協助客戶其電腦中斷時）、 帳戶移轉及系統漏洞的分析。專業服務方案，不包括結尾的下面的、 附註所涵蓋的客戶開發不得執行上的決策以產生法律或同樣重要個人效果的處理。|
|大規模處理[^1]特殊類別的資料 (揭露種族或民族血統、政治傾向、宗教或哲學信仰、或貿易同盟會員資格的個人資料，用於唯一識別自然人的基因資料、計量生物學資料，有關健康的資料或有關自然人性生活或性向的資料)，或與刑事定罪和犯罪行為有關的個人資料；|專業服務不得使用的工作所需的特殊類別的個人資料處理中排除客戶開發涵蓋下面的附註。<p>不過，資料控制器無法使用諮詢解決方案的專業服務處理之資料的列舉特殊類別。例如，專業服務提供醫療保健產業資料庫開發無法由資料控制器所用來處理個人健康情況相關聯的資料。它會評估控制站的責任及 [限制或文件視需要此使用方式。</p>|
| 大規模有系統地監視可公開進入的地區|專業服務不得使用中工作需要或以加速這類監控、 排除客戶開發涵蓋下面的附註。<p>如果資料控制器用以專業服務開發這種類型或 IT 系統用來處理透過這類監控比所收集的資料，是系統的說過資料控制站的責任如下所示。</p>|
|||

<!-- end of table -->
  
[自訂開發附註]專業服務會提供各種不同的諮詢解決方案。在資料控制站可能無法要求解決方案可符合上述準則，就是高風險的解決方案。例如，資料控制站可能會要求專業服務建立開發工作決策商務智慧引擎或信用的應用程式的解決方案或涉及使用者追蹤特殊人工地使用解決方案智慧 （電腦控制） / 分析、 或處理的個人資料的特殊類別。

參與開頭，專業服務具有用來評估的程序和地址高風險解決方案可能會被要求處理。這的一部分，專業服務可能需要從資料控制站上 GDPR 規範 （例如合約的條款）、 plan 保證開發 DPIA 或其他準則 （例如兩組所協作業系統方針） 所需的下 GDPR 資料處理器。不過，不論 Microsoft 的動作並適用的處理器為準的客戶資料從開發輸入 DPIA 資料控制站的責任。

## <a name="part-2--contents-of-a-dpia"></a>第 2 部分：DPIA 的內容

第 35 (7) 條規定「資料保護影響評估」對設想的處理和處理目的進行有系統的描述。完整的 DPIA 系統描述可能包含像是處理的資料類型、資料會保留多久、資料位置和傳輸目的地，以及哪些第三方可以存取資料。此外，DPIA 也必須包含：

-   評估與目的有關的處理操作的必要性和比例性；

-   評估自然人的權利和自由風險；和 

-   旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合本條例。

下表包含每個元素相關的專業服務的相關資訊。第 1 部分相同資料控制站必須考慮提供於下，以及其他相關因素控制站的特定實作的內容與 use(s) Professional 服務的詳細資訊。

***表 2-DPIA 相關專業服務的元素***

<!--start table here -->

|||
|:-----|:-----|
|**DPIA 的要素** |**專業服務的相關資訊**|
|處理的目的|處理使用專業服務資料的 purpose(s) 取決於實作、 設定和使用它的控制站。<p>所指定的[Microsoft 專業服務的資料保護 Addendum](http://aka.ms/professionalservicesdpa) (MPSDPA)、 Microsoft、 作為資料處理器、 處理支援及諮詢資料只以提供所要求的服務給我們的客戶資料控制站。Microsoft 不會使用支援與諮詢資料或衍生自它的任何廣告或類似的商業用途的資訊。</p>|
|處理使用專業服務資料的 purpose(s) 取決於實作、 設定和使用它的控制站。|所指定的[Microsoft 專業服務的資料保護 Addendum](http://aka.ms/professionalservicesdpa) (MPSDPA)、 Microsoft、 作為資料處理器、 處理支援及諮詢資料只以提供所要求的服務給我們的客戶資料控制站。Microsoft 不會使用支援與諮詢資料或衍生自它的任何廣告或類似的商業用途的資訊。|
|處理的個人資料類別|支援與查閱資料表示所有的資料，包括透過具有參與的所有文字、 聲音、 影片、 圖像檔、 或軟體的，或代表客戶提供給 Microsoft （或客戶授權從一種線上服務取得 Microsoft）若要取得專業服務或支援 Microsoft。這可能包括透過電話、 聊天室、 電子郵件或 web 表單收集的資訊。它還包括問題、 檔案傳輸至 Microsoft，以解決支援問題，自動化疑難排解員，或是存取遠端與客戶的權限的客戶系統的描述。<p>客戶資料及支援資料不包含客戶連絡人或計費資料，例如訂閱資訊和付款資料，以及哪些 Microsoft 收集並處理其容量 as 資料控制器何者為此文件的範圍內。</p>|
|資料保留|Microsoft 將持續時間內建立客戶投入加上參與結束視以確保品質之後保留期間及服務的持續保留支援與諮詢資料。例如，支援案例關閉資料之後是以確保能夠如果並未重新產生問題並重新開啟案例來參考它期間通常是保留資料。<p>專業服務提供支援，參與長度是針對定義時關閉支援案例。當專業服務提供諮詢服務時、 參與長度通常會由工作順序的定義。在其他情況下，參與長度是由商務關係的維護所定義。在所有的情況下，支援與諮詢資料將會刪除或傳回要求或符合客戶的指示不產生不堪延遲使用專業服務*資料主體權限指南*所述的功能。</p>|
|個人資料的位置和傳輸|由於專業服務，包括需要提供不間斷支援的性質可能全球通用傳輸資料。在要求上使用的 Microsoft 可運作的位置清單。針對諮詢服務、 資料可能會保留國內如果同意內的工作順序。<p>如個人資料從名為 European 經濟區域] 和 [瑞士]、 [Microsoft 可確保所傳送的第三個國家或全球組織的個人資料只限適當保護措施的 GDPR 文章 46 中所述。除了 [標準合約子句的處理器和其他模型合約[MPSDPA](http://aka.ms/professionalservicesdpa)所述的 Microsoft 的承諾、 Microsoft 認證歐盟美國瑞士美國隱私權盾 Framework 和承諾它們還必須。|
|與第三方共用資料|Microsoft 協力廠商做為我們子處理器支援功能，例如客戶與技術支援人員、 服務維護和其他作業與共用資料。會將會比[MPSDPA](http://aka.ms/professionalservicesdpa)中的資料保護條款沒有較少保護與 Microsoft 書寫協議輸入 Microsoft 轉接支援與諮詢資料之任何承包商。所有的協力廠商子處理器使用哪些支援和諮詢資料共用[MPSDPA](http://aka.ms/professionalservicesdpa)下包含[Microsoft 商業支援承包商清單](http://aka.ms/servicesapprovedsuppliers)中。<p>Microsoft 將不會公開支援與諮詢資料至執法機構除非依法規定。如果執法機構連絡 Microsoft 支援和諮詢資料需求與，Microsoft 將嘗試重新導向至直接從客戶要求該資料 law 執法機構。如果不得不透露支援與諮詢資料至執法機構、 Microsoft 會立即通知客戶與提供一份需求，除非法律上幫助禁止能力。<p>在任何其他協力廠商要求的支援和諮詢資料的回條，時 Microsoft 會立即通知客戶除非禁止依法規定。除非依法遵守 Microsoft 會拒絕要求。如果要求是有效的 Microsoft 將嘗試重新導向第三方直接向在客戶要求資料。</p>|
|資料主體權利|當作業系統為處理器、 Microsoft 提供給客戶 （資料控制器） 及其資料主旨和能夠滿足資料主體要求當他們會演練下 GDPR 其權限的個人資料。產品和處理器。 為我們角色與功能一致的方式我們所收到要求從受限於練習一或多個下 GDPR 其權限的客戶資料我們要求重新導向受限於產生的資料及其直接可讓我們要執行的動作 資料控制站。<p>*專業服務資料主體要求 GDPR 文件*提供客戶可以在如何處理 Professional 服務中的其資料主體權限責任的描述。</p>|
評估與目的有關的處理操作的必要性和比例性|這類評估取決於控制者的需求和處理的目的。<p>對於執行 Microsoft 處理這類處理是必要及調和間距基於提供資料控制器服務。Microsoft 認可變更為此行中[MPSDPA](http://aka.ms/professionalservicesdpa)。</p>|
|評估資料主體的權利和自由風險 |會函數的方式和資料控制器實作、 設定、 以及專業服務與專業人員所提供的任何解決方案會使用哪一種內容專業服務使用的權限和 freedoms 資料主題的重要風險。服務。<p>但是，與任何服務一樣，服務中保存的個人資料可能存在未經授權的存取或無意揭露的風險。下面討論 Microsoft 為解決這些風險所採取的措施。</p>|
| 旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合 GDPR。<!--is this the correct ending? -->|Microsoft 是致力客戶資訊的安全性。符合的文章 32 的 GDPR 佈建、 Microsoft 實作會維護及遵循適當的技術及組織量值用來保護支援與對意外、 未經授權或非法諮詢資料存取、 洩漏、 修改、 遺失或損毀。<p>此外，Microsoft 遵守適用於資料處理者的所有其他 GDPR 義務，包括但不限於提供資料保護影響評估和記錄保存。</p>|
|||

<!-- end of table -->

[^1]: With respect to the criteria that the processing be on a “large scale,” Recital 91 of the GDPR clarifies that: “The processing of personal data should not be considered to be on a large scale if the processing concerns personal data from patients or clients by an individual physician, other health care professional or lawyer. In such cases, a data protection impact assessment should not be mandatory.”


#### <a name="learn-more"></a>深入了解
[Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)