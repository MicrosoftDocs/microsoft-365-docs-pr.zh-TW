---
title: 使用 Office 365 的資料控制站的指導
description: 本文件提供資訊可協助他們決定是否需要 DPIA Professional 服務和功能包含詳細說明資料控制的站。
keywords: DPIA、 Office 365 Microsoft 365 文件 GDPR
author: BrendaCarter
ms.localizationpriority: high
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 4b96a80d0817a180d9a1400fa347d5345ecdec74
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866746"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-office-365"></a>使用 Microsoft Office 365 的資料控制站的資料保護影響評估： 指引 

一般資料保護法規 (GDPR)、 資料控制器所需準備處理作業中為"有可能導致高風險的權限和的自然人員 freedoms。"的資料保護影響評估 (DPIA)沒有固有一定會需要 DPIA 建立所使用的資料控制站的 Microsoft Office 365 中。 而是 DPIA 是否需要將會取決於詳細資料與內容資料控制站會部署、 設定，以及使用 Office 365 的方式。

若是如此，項目詳細資料包含以及本文件的用途是提供的資訊可協助他們決定是否需要 DPIA 的 Office 365 資料控制站。套用至 Office 365 應用程式及服務，包括但不是限於 Exchange Online、 SharePoint Online、 OneDrive for Business，Yammer Skype for Business 和 Power BI。 （請參閱，例如表格 1 及 2 的 Office 365 資料主體要求指南）。 
 
### <a name="part-1--determining-whether-a-dpia-is-needed"></a>第 1 部分 – 判斷是否需要 DPIA 

本文 35 GDPR 需要建立的資料保護影響評估"[w] 以下一種特別處理使用新的技術及考慮事項性質、 範圍、 內容及處理的目的是可能造成的資料控制站在高風險的權限和的自然人員 freedoms。 」將進一步設定出特定會指出這類高風險的因素下表中所討論。在決定是否需要 DPIA、 資料控制器應考慮這些因素，以及其他相關因素根據控制站的特定實作與 Office 365 use(s)。


***表 1-風險因素以及 Office 365 的相關資訊***

<!--start table here HEADER -->

|||
|:-----|:-----|:-----|
|**風險因素**|**關於 Office 365 的相關資訊**|
|適用於系統化且廣泛的評估與自然人員相關的個人層面這依據自動處理，包括分析，以及哪些決策以產生與相關的自然人員法律效果的或同樣天然人員會大幅影響 |取決於資料控制器組態，Office 365 可能會執行資料，例如分析所允許來導出前瞻上人員進行共同作業中的資料控制站的工作場所分析執行某些自動的處理從使用者的信箱的電子郵件和行事曆標題資訊為基礎的組織。<p>Office 365 並未設計來執行自動處理為基礎產生合法的決策或同樣重要個人效果。不過，Office 365 是高度自訂化服務，因為資料控制器無法可能會使用它進行這類處理。</p>|
|特殊類別的資料 （個人資料此處涉及或種族原點、 政治會員、 宗教或明智信念或商業機密等位成員資格及起源資料，如 purpose 的生物特徵資料處理大型 scale1 上的處理唯一識別自然人員、 關於健康情況資料或關於天然人員的性別 life 或性別方向資料），或含有刑事信念和 offences 個人資料 |Office 365 不特別設計來處理的個人資料的特殊類別。<p>不過，資料控制器無法使用 Office 365 處理之資料的列舉特殊類別。Office 365 是可讓客戶追蹤或否則處理任何類型的個人資料，包括個人資料的特殊類別的高度自訂化服務。使用任何會控制站判斷是否需要 DPIA 相關。但是作為資料處理器、 Microsoft 有這類使用沒有控制和通常會有少或沒有深入了解這類使用。</p>|
|在大型規模 * 的特殊類別的資料 （個人資料此處涉及或種族原點、 政治會員、 宗教或明智信念或商業機密等位成員資格及起源資料，如 purpose 的生物特徵資料處理處理唯一識別自然人員、 關於健康情況資料或關於天然人員的性別 life 或性別方向資料），或含有刑事信念和 offences 個人資料 |Office 365 不特別設計來處理的個人資料的特殊類別。<p>不過，資料控制器無法使用 Office 365 處理之資料的列舉特殊類別。Office 365 是可讓客戶追蹤或否則處理任何類型的個人資料，包括個人資料的特殊類別的高度自訂化服務。使用任何會控制站判斷是否需要 DPIA 相關。但是作為資料處理器、 Microsoft 有這類使用沒有控制和通常會有少或沒有深入了解這類使用。</p>|
|大規模有系統地監視可公開進入的地區|Office 365 並未設計來進行或便利這類監控。<p>不過，資料控制站可以使用它來處理透過這類監控收集的資料</p>|
|||

<!-- end of table -->[*]表示處理會依據 「 大刻度"的準則，囉 91 of GDPR 釐清的:"的個人資料處理不應該考慮要在大規模如果處理涉及病患或由用戶端的個人資料個別醫生、 其他醫療 professional 或律師。在這種情況下的資料保護影響評估不應該是必要項目。 」

### <a name="part-2--contents-of-a-dpia"></a>第 2 部分：DPIA 的內容 
本文 35(7) 斷定資料保護影響評估指定的處理的目的和適用於系統化構想處理的描述。 在 Microsoft 的 DPIAs 這類適用於系統化描述包含因素例如處理之資料類型、 資料會保留期限，其中的資料是位於以及傳送，且何種協力廠商提供可能會有資料的存取權。 此外，DPIA 必須包括： 
- 評估與目的有關的處理操作的必要性和比例性；  
- 評估自然人的權利和自由風險；和   
- 旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合本條例。 

下表提供可協助您 DPIA 草擬階段搭配使用 microsoft 的重要資訊。包含的每個 DPIA 必要元素相關的 Office 365 的相關資訊。 第 1 部分相同資料控制站必須考慮自己的特定實作的詳細資料和 Office 365 use(s) 下方所提供的詳細資料。

***表 2-元素和關於 Office 365 相關的因素***

<!--start table here HEADER -->

|||
|:-----|:-----|
|**風險因素**|**關於 Office 365 的相關資訊**|
|處理的目的|處理資料使用 Office 365 的 purpose(s) 取決於實作、 設定和使用它的控制站。<p>指定由[線上服務合約](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)，Microsoft、 作為資料處理器、 處理只以提供所要求的服務給我們的客戶資料控制站，包括相容於提供這些服務的用途的客戶資料。Microsoft 不會使用的客戶資料或衍生自它的任何廣告或類似的商業用途的資訊。</p>|
|處理的個人資料類別|[客戶資料]<br>這是包含文字、 聲音、 視訊或影像檔的所有資料及軟體的客戶提供給 Microsoft 或可提供透過其使用的 Microsoft online services 客戶的代理。它包含客戶儲存空間或處理，以及自訂項目上傳的資料。處理 Office 365 中的客戶資料的範例電子郵件內容包含在 Exchange Online，而且文件或檔案儲存在 SharePoint Online 或 OneDrive for Business。<p>[系統產生的記錄資料]<br>這是 Microsoft 就會產生執行服務，例如使用或效能資料的資料。大部分的這些資料包含 pseudonymous Microsoft 所產生的識別碼。<p>[支援資料]<br>這是資料或代表客戶提供給 Microsoft （或該客戶授權從一種線上服務取得 Microsoft） 透過與 Microsoft 以取得技術支援線上服務的參與。</p><p>客戶資料、 系統產生記錄檔資料及支援的資料不包含系統管理員和帳務資料，例如客戶系統管理員連絡資訊、 訂閱資訊及付款資料的 Microsoft 收集並為其容量的程序資料控制站和其超出此文件的範圍。</p>|
|資料保留|[客戶資料]<br>出在線上服務合約中的資料保護合約中的設定，Microsoft 會保持不變的客戶資料期間使用服務的客戶的右邊和客戶的所有資料之前已刪除或傳回符合客戶的指示或線上服務合約的條款。<p>所有時間期間的客戶的訂閱字詞客戶必須能夠存取、 「 解壓縮 」 及刪除儲存在服務中的客戶資料、 在某些情況下為特定產品功能的主旨適用對象以減輕由於意外的風險（例如 Exchange 已復原的項目] 資料夾），以進一步說明產品文件中刪除。</p><p>除了免費試用版與 LinkedIn 服務] Microsoft 將保留客戶資料儲存在線上服務在有限的函數帳戶 90 天的到期日或客戶的訂閱的終止之後，讓客戶可以擷取資料。90 天保留期間結束後，Microsoft 會停用 「 客戶帳戶並刪除客戶資料。</p><p>[系統產生的記錄資料]<br>此資料會保留為預設期間的最多 180 天，從集合受限於較長的保留期間其中所需的安全性的服務或符合法律或法規責任。</p><p>如需可讓客戶來刪除任何時候維護服務中的個人資料服務功能的進一步資訊，請參閱[Office 365 資料主體要求指南 》](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests?toc=/microsoft-365/enterprise/toc.json)。|
|個人資料的位置和傳輸|Microsoft 中所述的資料保護條款的線上服務合約，如果客戶佈建澳大利亞、 加拿大、 歐盟、 法國、 印度、 日本、 南韓國、 英國、 或美國中的 Office 365 其執行個體，將會儲存只有在該位置的靜態追蹤客戶資料： （1) Exchange Online 信箱內容 （電子郵件內文、 行事曆項目及內容的電子郵件附件）、 （2) SharePoint Online 網站內容與網站 （3） 檔案上傳至的檔案內儲存OneDrive 商務和 (4) project 內容的上傳至 Project Online。<p>如其他類型的個人資料從名為 European 經濟區域] 和 [瑞士]、 [Microsoft 可確保所傳送的第三個國家或全球組織的個人資料只限適當保護措施的 GDPR 文章 46 中所述。除了 [標準合約子句的處理器和其他模型合約 Microsoft 承諾、 Microsoft 認證歐盟美國和瑞士美國隱私權盾 Framework，以及它們與承諾。</p>|
|透過協力廠商 subprocessors 共用資料|Microsoft 支援功能，例如客戶與技術支援人員、 服務維護和其他作業做為我們 subprocessors 協力廠商與共用資料。Microsoft 轉接的客戶資料或支援資料之任何承包商將已輸入至已於[線上服務合約](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)中的資料保護條款沒有較少保護與 Microsoft 書寫協議。[Online Services 轉包商] 清單](https://aka.ms/Online_Serv_Subcontractor_List)中包含所有的協力廠商 subprocessors 與共用 Microsoft 的核心線上服務的客戶資料。所有可以存取支援的資料 （包括客戶會選擇要在其支援互動期間共用的客戶資料） 的第三方 subprocessors 包含在[Microsoft 商業支援承包商清單](http://aka.ms/servicesapprovedsuppliers)中。 |
|透過獨立的協力廠商提供共用資料|某些 Office 365 產品包括在控制器進行選擇啟用的擴充性選項與獨立的協力廠商提供共用的資料。 例如，Exchange Online 是可延伸的平台，可讓協力廠商增益集或如何將與 Outlook 整合和擴充 Outlook 的功能集的連接器。獨立 Microsoft、 act 增益集或連接器這些協力廠商提供者和其增益集或連接器必須啟用的使用者或 enterprise 管理員，負責使用其增益集或連接器的帳戶進行驗證。<p>Microsoft 將不會公開的客戶資料或支援資料至執法機構除非依法規定。如果執法機構連絡 Microsoft 客戶資料或支援資料需求與，Microsoft 將嘗試重新導向至直接從客戶要求該資料 law 執法機構。如果不得不透露客戶資料或支援資料至執法機構、 Microsoft 會立即通知客戶與提供一份需求，除非法律上幫助禁止能力。</p><p>收到其他第三方要求客戶資料或支援資料時，Microsoft 會立即通知客戶，除非法律禁止。除非法律規定，否則 Microsoft 會拒絕要求。如果要求有效，Microsoft 會指引第三方直接向客戶要求的資料。</p>|
|資料主體權利|當作業系統為處理器、 Microsoft 提供給客戶 （資料控制器） 及其資料主旨和能夠滿足資料主體要求當他們會演練下 GDPR 其權限的個人資料。我們不要讓產品和處理器。 為我們角色與功能一致的方式如果我們收到要求來自若要運用一或多個下 GDPR 其權限的客戶資料主旨我們要求重新導向受限於產生的資料及其直接以某e 資料控制站。<p>[Office 365 資料主體要求指南](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests?toc=/microsoft-365/enterprise/toc.json)提供資料控制器說明如何支援資料主體權限在 Office 365 中使用的功能。</p>|
|評估與目的有關的處理操作的必要性和比例性|這類評估取決於控制者的需求和處理的目的。<p>對於執行 Microsoft 處理這類處理是必要及調和間距基於提供資料控制器服務。</p>|
|評估資料主體的權利和自由風險 |從 Office 365 使用的權限和 freedoms 資料主題的重要風險會函數方式與在哪一種內容資料控制器實作、 設定，以及使用它。<p>但是，與任何服務一樣，服務中保存的個人資料可能存在未經授權的存取或無意揭露的風險。下面討論 Microsoft 為解決這些風險所採取的措施。</p>|
|旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合 GDPR。|Microsoft 致力於幫助保護客戶資訊安全。根據 GDPR 第 32 條的規定，Microsoft 已經並將保持並遵循適當的技術和組織措施，旨在保護客戶資料和支援資料，避免遭受意外、未經授權或非法的存取、洩漏、更改、遺失或銷毀。<p>此外，Microsoft 遵守適用於資料處理者的所有其他 GDPR 義務，包括但不限於提供資料保護影響評估和記錄保存。</p>|
|||

<!-- end of table -->

#### <a name="learn-more"></a>深入了解
[Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)