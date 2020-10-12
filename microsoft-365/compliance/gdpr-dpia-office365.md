---
title: 適用於使用 Office 365 之資料控制者的指引
description: 本文件為資料控制者提供 Office 365 相關資訊，協助他們判斷是否需要 DPIA，以及應包含哪些詳細資料。
keywords: DPIA、Office 365、Microsoft 365 文件、GDPR
ms.localizationpriority: Priority
ms.prod: microsoft-365-enterprise
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
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a51b01d419cc81efd82c7ed78f5b05d337353b39
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413481"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-office-365"></a>資料保護影響評估：適用於使用 Microsoft Office 365 之資料控制者的指引 

在一般資料保護規定 (GDPR) 下，資料控制者若要處理「可能會對自然人的權利和自由造成高度風險」的作業時，必須準備資料保護影響評估 (DPIA)。Microsoft Office 365 本身不具有使用其資料的資料控制者應該建立 DPIA 的要求。然而，是否需要 DPIA，須視您，身為控制者，如何部署、設定、使用 Office 365 的詳細資料和相關內容而定。

本文件的第 1 部分提供 Office 365 的相關資訊，以協助身為資料控制者的您判斷是否需要 DPIA。  如果您的回答是「是」，則本文件的第 2 和 第 3 部分提供來自Microsoft 的重要資訊，可協助您草擬 DPIA。 具體來說，第 2 部分針對 DPIA 所需的每個必要元素提供適用於所有 Office 365 服務的解答。 第 3 部分則針對客戶草擬自己的 DPIA 時需要的數個最相關資訊，提供額外的特定產品資訊。 第 3 部分也包含 DPIA 說明文件，您可以下載並加以修改，讓您更輕鬆地草擬 DPIA。

Office 365 應用程式和服務包括但不限於 Exchange Online、SharePoint Online、商務用 OneDrive、Yammer 和 Microsoft Teams。 可在 [GDPR 和 CCPA 的 Office 365 資料主體要求](gdpr-dsr-office365.md)中的表 1 和表 2 中看到 Office 365 提供之服務的較完整清單。

## <a name="part-1-determining-whether-a-dpia-is-needed"></a>第 1 部分：判斷是否需要 DPIA

GDPR 第 35 條規定，「如果某種處理，特別是使用新技術，並考慮到處理的性質、範圍、背景和目的，可能會對自然人的權利和自由造成高度風險」，則資料控制者必須建立「資料保護影響評估」。 它還進一步列出表明如此高風險的特定因素，將在下表進行討論。 在判斷是否需要 DPIA 時，您身為資料控制者，應根據控制者對特定 Office 365 的實作和使用，考慮這些因素以及任何其他相關因素。

|||
|:-----|:-----|:-----|
|**風險因素**|**Office 365 的相關資訊**|
|系統地、廣泛地評估與自然人有關的個人方面，該評估基於自動處理 (包括概況分析)，並基於這些決策產生與自然人有關的法律效力或類似地對自然人產生重大影響的決策 |依據資料控制者的設定而定，Office 365 可能會執行特定的資料自動化處理，例如由「工作場所分析」執行的分析，讓資料控制者根據使用者信箱的電子郵件和行事曆標頭資訊，對組織內人員的共同作業方式衍生出深入解析。 <br><br> Office 365 並非旨在執行自動處理，以作為對個人產生法律或類似重大影響之決策的基礎。 不過，因為 Office 365 是個能高度自訂的服務，資料控制者可能會將其用於此類處理。 |
|大規模處理 <sup>1</sup> 特殊類別的資料 (揭露種族或民族血統、政治傾向、宗教或哲學信仰或貿易同盟會員資格的個人資料，以及用於唯一識別自然人的遺傳資料、生物特徵辨識資料的處理、有關健康的資料或有關自然人性生活或性向的資料)，或與刑事定罪和犯罪行為有關的個人資料 |Office 365 並非設計用來處理特殊類別的個人資料。 <br><br> 不過，資料控制者也可以使用 Office 365 來處理列舉的特殊類別資料。 Office 365 是個能高度自訂的服務，可讓客戶追蹤，或處理任何類型的個人資料，包括特殊類別的個人資料。 控制者自行判斷是否需要 DPIA。 但身為資料處理者，Microsoft 對於這類使用無控制權，且通常僅有少許或完全沒有對該使用的瞭解。 |
|大規模有系統地監視可公開進入的地區|Office 365 並非特別設計用來進行或協助這類監視。 <br><br> 不過，資料控制可以使用它來處理透過這類監視收集到的資料。 |
|||

>[!Note]
><sup>1</sup> 關於「大規模」處理的準則，GDPR 第 91 條闡明：「如果處理是有關於個別醫生、其他醫療保健專業人員或律師之病患或客戶的個人資料，則處理個人資料不應視為大規模。 在此類情況下，資料保護影響評估不應強制。」

## <a name="part-2-contents-of-a-dpia"></a>第 2 部分：DPIA 的內容

GDPR 第 35(7) 條要求資料保護影響評估需指出處理的目的和對預期處理的系統描述。 在 Microsoft 的 DPIA 中，此類系統描述包括諸如處理的資料類型、保留資料的時間、資料的位置和傳輸位置，以及哪些第三方可以存取資料等因素。 此外，DPIA 也必須包含：

- 評估與目的有關的處理操作的必要性和比例性；
- 評估自然人的權利和自由風險；和 
- 旨在解決風險的措施，包括保障措施、安全性措施和機制，以確保個人資料受到保護，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合「一般資料保護規定」。

下表提供來自 Microsoft 的重要資訊，可協助您草擬 DPIA。 其中包含與 DPIA 所需每個必要元素相關的 Office 365 相關資訊。 在第 1 部分中，資料控制者必須考量以下提供的詳細資料，以及 Office 365 特定實作和使用的詳細資料。

|||
|:-----|:-----|
|**風險因素**|**Office 365 的相關資訊**|
| 處理的目的 | 使用 Office 365 進行處理的目的取決於實作、設定及使用 Office 365 的控制者。 <br><br> 根據[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和[資料保護附錄](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=67)的規定，Microsoft 作為資料處理者，可根據客戶提供的指示處理客戶資料，為客戶提供線上服務。 <br><br> 如標準[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和[資料保護增訂版](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=67)所詳列，Microsoft 也會使用個人資料來支援限定的合法商務作業，包括：(1) 帳單和帳戶管理；(2) 薪酬 (例如，計算員工傭金和合作夥伴獎勵)；(3) 內部報告與建模 (例如，預測、收入、產能規劃、產品策略)；(4) 防範可能對 Microsoft 或 Microsoft 產品產生影響的欺詐、網路犯罪或網路攻擊；(5) 改善協助工具、隱私權或能源效率的核心功能；以及 (6) 財務報告和法律義務遵循 (遵守線上服務條款所述之客戶資料披露的相關限制)。 <br><br> Microsoft 可控制個人資料的處理方式，以支援前述特定的合法商務作業。 一般情況下，Microsoft 會先彙總個人資料，再將其用於我們合法的商務作業，而去除 Microsoft 識別特定人員的能力，此外，在使用個人資料支援合法商務作業所需的處理時，會採用最低限度識別性的形式。 <br><br> Microsoft 不會將客戶資料或其衍生的資料用於分析、廣告或類似的商業用途。 |
| 處理的個人資料類別 | **客戶資料：** 這是所有資料，包括文字、音訊、視訊或影像檔和軟體，由客戶提供給 Microsoft 或是透過使用 Microsoft 線上服務代表客戶提供。 包括客戶上傳用於存儲或處理以及自訂的資料。 在 Office 365 中處理客戶資料的範例，包括 Exchange Online 中的電子郵件內容，和 SharePoint Online 或商務用 OneDrive 中儲存的文件或檔案。 <br><br> **服務產生的資料：** 這是 Microsoft 透過服務的運作而產生或衍生的資料，例如使用或效能資料。 這些資料大部分都包含由 Microsoft 產生的 pseudonymous 識別碼。 <br><br> **診斷資料：** Microsoft 會從連線至線上服務的客戶在本機安裝的軟體收集或取得這項資料，我們也可稱之為遙測。 這個資料通常可由本機安裝的軟體或執行該軟體的電腦所具備的屬性來識別。 <br><br> **支援資料：** 這是為了獲得線上服務的技術支援，由客戶或代表客戶 (或客戶授權 Microsoft 從線上服務取得) 透過與 Microsoft 的合作向 Microsoft 提供的資料。 <br><br> 客戶資料、系統所產生的記錄資料和支援資料不包含系統管理員和帳單資料，例如客戶系統管理員連絡資訊、訂閱資訊和付款資料，Microsoft 會利用其資料控制者身分 (本文件範疇外) 所具備的功能收集和處理這些資料。 |
| 資料保留 | **客戶資料：** 如同在線上服務條款的資料保護條款中所羅列，Microsoft 將會在客戶有權使用服務的一段時間保留客戶資料，直到所有客戶資料依據客戶指示或線上服務條款進行刪除或傳回。 <br><br> 在客戶訂閱的期間，客戶得以存取、擷取及刪除服務中儲存的客戶資料，在某些情況下，特定產品功能旨在降低不經意刪除的風險 (例如，Exchange 復原項目資料夾)，在產品文件中有進一步的說明。 <br><br> 除了免費試用版和 LinkedIn 服務，Microsoft 將在客戶訂閱到期或終止訂閱後的 90 天內，將儲存在線上服務中的客戶資料保留在功能有限的帳戶中，以便客戶可以存取資料。 90 天的保留期間結束後，Microsoft 將停用客戶的帳戶並刪除客戶資料。 <br><br> **服務產生的資料：** 此資料會保留從收集起算最多 180 天的預設期間，受限於針對服務安全性或符合法律或法規義務而需要較長的保留期間。 <br><br> 如需可讓客戶隨時刪除在服務中維護之個人資料的服務功能進一步資訊，請參閱 [Office 365 的資料主體要求指南](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests?toc=/microsoft-365/enterprise/toc.json)。|
| 個人資料的位置和傳輸 | 如同線上服務條款的附件 1 所述，如果客戶在澳洲、加拿大、歐盟、法國、印度、日本、南韓、英國或美國佈建其 Office 365 執行個體，Microsoft 只會在該位置內儲存下列客戶資料：(1) Exchange Online 信箱內容 (電子郵件本文、行事曆項目及電子郵件附件的內容)，(2) SharePoint Online 網站內容和儲存在該網站內的檔案，(3) 上傳至商務用 OneDrive 的檔案，以及 (4) 上傳至 Project Online 的專案內容。 <br><br> 針對來自歐洲經濟區和瑞士的其他類型個人資料，Microsoft 會確保個人資料傳輸給第三國或國際組織時受到 GDPR 第 46 條所述適當保護措施的保護。Microsoft 除了遵守處理者的「標準合約條款」以及其他定型化契約的承諾外，還通過了「歐盟-美國」和「瑞士-美國」隱私盾框架及其限定承諾的認證。 |
| 與第三方子處理者共用資料 | Microsoft 與作為本公司次處理者的第三方共用資料，以支援諸如客戶和技術支援、服務維護及其他作業等功能。 任何轉包商只要接收到 Microsoft 傳輸的客戶資料、支援資料或個人資料，都將與 Microsoft 達成書面協議，其保護力不低於[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)中的資料保護條款。 所有共用 Microsoft 核心線上服務所含之客戶資料的第三方次要處理者，都會納入[線上服務轉包商](https://aka.ms/Online_Serv_Subcontractor_List)清單中。 所有可存取支援資料 (包括客戶在其支援互動中選擇要共用的客戶資料) 的第三方次要處理者，都會納入 [Microsoft 商業支援承包商清單](https://aka.ms/servicesapprovedsuppliers)中。 |
| 與獨立第三方共用資料 | 部分 Office 365 產品具有擴充選項，可在控制者的選取下，與獨立的第三方共用資料。  例如，Exchange Online 就是一種可延伸的平台，可讓第三方增益集或連接器與 Outlook 整合，並擴充 Outlook 的功能集。 這些增益集或連接器的第三方提供者可獨立運作不受 Microsoft 管理，其增益集或連接器必須由使用其增益集或連接器帳戶進行驗證的使用者或企業系統管理員啟用。 <br><br> 除非法律要求，否則 Microsoft 不會向執法機關揭露客戶資料或支援資料。如果執法機關聯繫 Microsoft 提出客戶資料或支援資料的需求，Microsoft 會嘗試引導執法機關直接向客戶要求資料。如果被迫向執法機關揭露客戶資料或支援資料，Microsoft 會立即通知客戶，並提供一份需求副本，除非法律禁止這樣做。 <br><br> 收到其他第三方要求客戶資料或支援資料時，Microsoft 會立即通知客戶，除非法律禁止。除非法律規定，否則 Microsoft 會拒絕要求。如果要求有效，Microsoft 會指引第三方直接向客戶要求的資料。 |
| 資料主體權利 | 以處理者的身分操作時，Microsoft 會為客戶 (資料控制者) 提供資料主體的個人資料，及其依據 GDPR 行使其權利時履行資料主體要求的能力。 我們執行此作業的方式與產品功能一致，且角色如同是處理者。如果我們收到客戶資料主體中的要求，指出想要依據 GDPR 行使其一或多項權利，我們會將資料主體重新導向，以將其要求直接送至資料控制者。 Office 365 的資料主體要求指南向資料控制者提供如何使用 Office 365 的功能支援資料主題權利的說明。 <br><br> 若來自資料主體的要求旨在依據 GDPR 對處理後用以支援合法商務程序的個人資料行使權利，則該要求應按照 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)中的說明導向至 Microsoft。 <br><br> Microsoft 通常會先彙總個人資料，再將其用於我們合法的商務作業，且無法在彙總資料中識別特定人員的個人資料。 這樣可以大幅降低個人承受的隱私權風險。  Microsoft 在無法識別個人身分的情況下，便無法支援存取、清除、可攜性、處理限制或異議等方面的資料主體權利。 |
| 評估與目的有關的處理操作的必要性和比例性 | 這類評估取決於控制者的需求和處理的目的。 <br><br> 關於 Microsoft 進行的處理，這種處理對於向資料控制者提供服務的目的是必要的且符合比例原則。 |
| 評估資料主體的權利和自由風險  | 資料主體使用 Office 365 在權利和自由方面的主要風險將取決於資料控制者如何以及在何種情況下實作、設定及使用 Office 365。 <br><br> Microsoft 對於其用來支援合法商務作業以利佈建服務的個人資料，會採用匿名化或彙總之類的機制，並盡可能降低使用服務的資料主體進行此類處理的風險。 <br><br> 但是，與任何服務一樣，服務中保存的個人資料可能存在未經授權的存取或無意揭露的風險。 以下章節會討論 Microsoft 為解決這些風險所採取的措施。 |
| 旨在解決風險的措施，包括保障措施、安全性措施和機制，以確保個人資料受到保護，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合 GDPR | Microsoft 致力於協助保護客戶資訊的安全性。 根據 GDPR 第 32 條的規定，Microsoft 已經並將保持並遵循適當的技術和組織措施，旨在保護客戶資料和支援資料，避免遭受意外、未經授權或非法的存取、洩漏、更改、遺失或銷毀。 <br><br> 此外，Microsoft 遵守適用於資料處理者的所有其他 GDPR 義務，包括但不限於提供資料保護影響評估和記錄保存。 <br><br> Microsoft 在處理個人資料以供合法的商務作業使用時，會善盡資料控制者適用的 GDPR 義務。 |

## <a name="part-3-dpias-are-hard-but-this-may-help"></a>第 3 部分：DPIA 很困難，但本節內容能有所幫助

如果您已判斷組織必須草擬 DPIA，本節中的資訊旨在協助您輕鬆地完成這項程序。

本節內容：

- 提供 Office 365 和產品特定資訊相關服務元素，以及
- 提供您可下載、修改及用來草擬 DPIA 的空白模型 DPIA 範本。 

### <a name="dpia-service-elements-matrix"></a>DPIA 服務元素矩陣

[DPIA 服務元素矩陣](../downloads/dpia-service-elements-matrix-final-10-2020.xlsx)是一種內容組織，在您開始記錄 DPIA 的過程中可能會有所幫助。 這項功能依服務方式分類，提供產品特定資訊和文件連結，可幫助您更輕鬆地草擬對必要 DPIA 元素的回應式答案。

### <a name="customizable-dpia-document"></a>可自訂的 DPIA 文件

我們知道，草擬 DPIA 可能會是個非常耗時的工作。 雖然每個客戶的 DPIA 會根據每個組織設定和 Office 365 的使用方式而有所不同，但是以下文件可節省您的時間。 您可以下載[可自訂的 DPIA 文件](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/customizable-dpia-document-final-10-2020.docx)做為可修改的說明範本，以便快速開始。 您可以免費使用並適應您的特定服務實作。 本文件不應解釋為 Microsoft 或其任何附屬公司提供的法律建議。 如果您有任何關於 DPIA 草擬程序的問題，建議您諮詢您的律師。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
