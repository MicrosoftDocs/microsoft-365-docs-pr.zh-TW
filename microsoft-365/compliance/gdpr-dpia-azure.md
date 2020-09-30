---
title: 符合 GDPR 的 Azure DPIA
description: 在使用 Microsoft Azure 時，尋找相關資訊以判斷是否需要資料保護影響評估 (DPIA)。
keywords: DPIA, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a51a04e0040f9f5d435c77f9894108fe1baeef9
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305063"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-azure"></a>資料保護影響評估：資料控制者使用 Microsoft Azure 的指引

在一般資料保護規定 (GDPR) 下，資料控制者若要處理「可能會對自然人的權利和自由造成高度風險」的作業，必須準備資料保護影響評估 (DPIA)。Microsoft Azure 本身不具有使用其資料的資料控制者必須建立 DPIA 的要求。然而，是否需要 DPIA，須視控制者「如何」** 部署、設定、使用 Microsoft Azure 的詳細資料和相關內容而定。

本文件旨在提供資料控制者有關 Microsoft Azure 的資訊，協助他們判斷是否需要 DPIA，以及若需要，應包含哪些詳細資料。

>[!Note]
>Microsoft 在本文件中不提供任何法律建議。 本文件僅供參考。 我們鼓勵客戶與其隱私權主管和法律顧問合作，以確定與使用 Microsoft Azure或其他任何 Microsoft 線上服務相關之任何 DPIA 的必要性和內容。

## <a name="part-1-determining-whether-a-dpia-is-needed"></a>第 1 部分：判斷是否需要 DPIA

GDPR 第 35 條規定，「如果某種處理，特別是使用新技術，並考慮到處理的性質、範圍、背景和目的，可能會對自然人的權利和自由造成高度風險」，資料控制者需要建立「資料保護影響評估」(DPIA)。 它進一步闡述會發生這類高風險的特定因素，如下表所述。若要判斷是否需要 DPIA，資料控制者應根據控制者的特定 Microsoft Azure 實作和使用，考慮這些因素，以及任何其他相關因素。

|||
|:----|:----|
|**高風險因素**|**Microsoft Azure 的相關資訊**|
| 基於自動化處理對自然人的個人方面進行系統和廣泛的評估，包括概況分析，以及對自然人產生法律效果的決定或對自然人產生同樣重大影響的決定。| Microsoft Azure 未提供用來執行某些資料自動處理的功能。 <br><br> *不過，由於 Azure 是高度自訂的服務，資料控制者有可能將其設定用於這類處理*。控制者應根據他們對 Azure 的使用情況做出決定。 |
| 大規模處理特殊類別的資料 (揭露種族或民族血統、政治傾向、宗教或哲學信仰，或貿易同盟會員資格的個人資料，用於唯一識別自然人的基因資料、計量生物學資料，有關健康的資料或有關自然人性生活或性向的資料)，或與刑事定罪和犯罪行為有關的個人資料。 | Microsoft Azure 並非設計用來處理特殊類別的個人資料，Azure 的使用方式並不會增加控制者處理的固有的風險。 <br><br> 不過，資料控制者可以使用 Microsoft Azure 處理列舉的特殊類別資料。** Microsoft Azure 是高度自訂的服務，可讓客戶追蹤、或處理任何類型的資料，包括特殊類別的個人資料。但身為資料處理者，Microsoft 對這類使用沒有控制權，且無法知道或預期有這類使用。資料控制者有義務確定資料控制者的資料被適當使用。 |
| 大規模有系統地監視可公開進入的地區。  | Microsoft Azure 並非特別設計用來進行或協助這類監視。 <br><br> 不過，資料控制可以使用 Azure 來處理透過這類監視收集到的資料。** Microsoft Azure 是高度自訂的服務，可讓客戶追蹤、或處理任何類型的資料，包括監視資料。但身為資料處理者，Microsoft 對這類使用沒有控制權，且無法知道或預期有這類使用。資料控制者有義務確定資料控制者的資料被適當使用。 |

## <a name="part-2-contents-of-a-dpia"></a>第 2 部分：DPIA 的內容

第 35(7) 條要求資料保護影響評估需指出處理的目的，以及構想處理程序之有系統的描述。 完整的 DPIA 系統描述可能包含像是處理的資料類型、資料會保留多久、資料位置和傳輸目的地，以及哪些第三方可以存取資料。 此外，DPIA 也必須包含：

- 評估與目的有關的處理操作的必要性和比例性；
- 評估自然人的權利和自由風險；和 
- 旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合本條例。

下表包含與每個要素相關的 Microsoft Azure 資訊。如同第 1 部分，資料控制者必須根據控制者的特定 Microsoft Azure 實作和使用，考慮下列詳細資料，以及任何其他相關因素。

||||
|:---|:---|:--|
|**DPIA 的要素**|**Microsoft Azure 的相關資訊**| |
| 處理的目的 | 使用 Microsoft Azure 進行處理的目的取決於實作、設定及使用 Microsoft Azure 的控制者。 <br><br> 根據[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和[資料保護增訂版](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=67)的規定，Microsoft 作為資料處理者，可根據客戶提供的指示處理客戶資料，為客戶提供線上服務。 <br><br> 如標準[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和[資料保護增訂版](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=67)所詳列，Microsoft 也會使用個人資料來支援限定的合法商務作業，包括：(1) 帳單和帳戶管理；(2) 薪酬 (例如，計算員工傭金和合作夥伴獎勵)；(3) 內部報告與建模 (例如，預測、收入、產能規劃、產品策略)；(4) 防範可能對 Microsoft 或 Microsoft 產品產生影響的欺詐、網路犯罪或網路攻擊；(5) 改善協助工具、隱私權或能源效率的核心功能；以及 (6) 財務報告和法律義務遵循 (遵守線上服務條款所述之客戶資料披露的相關限制)。 <br><br> Microsoft 可控制個人資料的處理方式，以支援前述特定的合法商務作業。 一般情況下，Microsoft 會先彙總個人資料，再將其用於我們合法的商務作業，而去除 Microsoft 識別特定人員的能力，此外，在使用個人資料支援合法商務作業所需的處理時，會採用最低限度識別性的形式。 <br><br> Microsoft 不會將客戶資料或其衍生的資料用於分析、廣告或類似的商業用途。 |   |
| 處理的個人資料類別  | *客戶資料：由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。  客戶資料包括 (1) 使用者的識別資訊 (例如 Azure Active Directory 中的使用者名稱和連絡人資訊)，以及客戶上傳到特定服務或在特定服務中建立的客戶內容 (例如，Azure 儲存體帳戶中的客戶內容、Azure SQL Database 的客戶內容，或客戶在 Azure 虛擬機器中的虛擬機器映像)。<br><br> *服務產生的資料：Microsoft 產生的記錄及相關資料，可協助 Microsoft 向使用者提供企業服務。 服務產生的記錄，主要包含經過假名化處理，且與系統所產生的唯一識別碼相關聯的資料，無法單獨用來識別個人，但可用來向使用者提供企業服務。 這些產生的記錄也可能包含使用者的身分識別資訊 (例如使用者名稱)。 <br><br> *支援資料：這是為了獲得線上服務的技術支援，由客戶或代表客戶 (或客戶授權 Microsoft 從線上服務取得) 透過與 Microsoft 的合作向 Microsoft 提供的資料。 <br><br> 如需有關 Azure 處理資料的詳細資訊，請參閱[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)，包括資料處理合約以及 [Microsoft 信任中心](https://www.microsoft.com/trustcenter)。</p> |   |
| 資料保留 | Microsoft 將在客戶使用線上服務的權利期間保留及處理客戶資料，直到客戶擷取資料或根據 OST 條款刪除客戶資料。  在客戶訂閱期間，客戶可隨時存取及擷取儲存在每個線上服務中的客戶資料。 除了免費試用版和 LinkedIn 服務，Microsoft 將在客戶訂閱到期或終止訂閱後的 90 天內，將儲存在線上服務中的客戶資料保留在功能有限的帳戶中，以便客戶可以存取資料。 90 天的保留期間結束後，Microsoft 將停用客戶的帳戶並刪除客戶資料。 客戶可以使用 [Azure 資料主體要求 GDPR 文件](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)中描述的功能，根據資料主體要求刪除個人資料。 |   |
| 個人資料的位置和傳輸 | 客戶能夠在指定的[地理區域](https://azuredatacentermap.azurewebsites.net/)內佈建靜態客戶資料，但需遵守 OST 中規定的某些例外情況。 客戶亦可在線上服務條款 (OST) 和 [Azure 全球基礎結構](https://azure.microsoft.com/global-infrastructure/)網頁的附件 1 中，找到有關服務部署和資料常駐的其他詳細資訊。<br><br>針對來自歐洲經濟區和瑞士的個人資料，Microsoft 會確保個人資料傳輸給第三國或國際組織時受到 GDPR 第 46 條所述適當保護措施的保護。 Microsoft 除了遵守處理者的「標準合約條款」以及其他定型化契約的承諾外，也已通過「歐盟-美國」和「瑞士-美國」隱私盾架構及其限定承諾的認證。 |   |
| 與第三方子處理者共用資料 | Microsoft 與作為本公司次處理者的第三方共用資料，以支援諸如客戶和技術支援、服務維護及其他作業等功能。 任何轉包商只要接收到 Microsoft 傳輸的客戶資料、支援資料或個人資料，都將與 Microsoft 達成書面協議，其保護力不低於[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)中的資料保護條款。 所有共用 Microsoft 核心線上服務所含之客戶資料的第三方次要處理者，都會納入「線上服務轉包商」清單中。 所有可存取支援資料 (包括客戶在其支援互動中選擇要共用的客戶資料) 的第三方次要處理者，都會納入 [Microsoft 商業支援承包商](https://www.microsoft.com/trustcenter/privacy/who-can-access-your-data-and-on-what-terms#subcontractors)清單中。  |   |
| 資料主體權利 | 以處理者的身分操作時，Microsoft 會為客戶 (也稱為資料控制者) 提供資料主體的個人資料，及其依據 GDPR 行使其權利時履行資料主體要求的能力。 Microsoft 執行此作業的方式與產品功能一致，且其角色如同是資料處理者。如果 Microsoft 收到客戶資料主體中的要求，指出想要依據 GDPR 行使其一或多項權利，該要求將會重新導向至資料控制者。 <br><br> 資料控制者可參考 Azure 的資料主體要求指南，以了解如何使用 Azure 中的功能來支援資料主體權利。 <br><br> 若來自資料主體的要求旨在依據 GDPR 對處理後用以支援合法商務程序的個人資料行使權利，則該要求應按照 Microsoft 隱私權聲明中的說明導向至 Microsoft。 <br><br> Microsoft 通常會先彙總個人資料，再將其用於我們合法的商務作業，且無法在彙總資料中識別特定人員的個人資料。 此動作可以大幅降低個人承受的隱私權風險。  Microsoft 在無法識別個人身分的情況下，便無法支援存取、清除、可攜性、處理限制或異議等方面的資料主體權利。 <br><br> [Azure 資料主體要求 GDPR 文件](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)中說明如何使用 Azure 的功能支援資料主題權利。 |   |
| 評估與目的有關的處理操作的必要性和比例性 | 這類評估取決於資料控制者的需求和處理的目的。<br><br> Microsoft 對於其用來支援合法商務作業以利佈建服務的個人資料，會採用匿名化或彙總之類的機制，並盡可能降低使用服務的資料主體進行此類處理的風險。 <br><br> 關於 Microsoft 進行的處理，這種處理對於向資料控制者提供服務的目的是必要的且符合比例原則。Microsoft 在 OST 中做出此一承諾。 | |
| 評估資料主體的權利和自由風險  | 資料主體使用 Microsoft Azure 在權利和自由方面的主要風險將取決於資料控制者如何以及在何種情況下實作、設定及使用 Microsoft Azure。<br><br> 但是，與任何服務一樣，服務中保存的個人資料可能存在未經授權的存取或無意揭露的風險。 OST 中討論 Microsoft 為解決這些風險所採取的措施，如本文稍後所述。 | |
| 旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合 GDPR | Microsoft 致力於幫助保護客戶資料的安全。Microsoft 所採取的安全性措施詳述於 OST 中。<br><br> Microsoft 採行嚴格的安全性標準和領先業界的資料保護方法。 Microsoft 持續不斷地改善其系統，以因應新的威脅。 如需關於雲端控管與隱私權實務準則的詳細資訊，請前往[信賴中心的雲端管理和隱私權](https://www.microsoft.com/trustcenter/guidance/ensure-compliance)頁面。 <br><br> Microsoft 採取合理和適當的技術和有組織的措施來保護其處理的個人資料。這些措施包括，但不限於內部的隱私權原則和做法、合約承諾、以及國際與地區性的標準認證。詳細資訊請參閱[信任中心的隱私權標準網頁](https://www.microsoft.com/trustcenter/privacy/we-set-and-adhere-to-stringent-standards)。<br><br> Microsoft 提供重要、透明的面向客戶的安全性和隱私權材料，以幫助解釋 Microsoft 對個人資料的使用和處理。 我們歡迎客戶與 Microsoft 連絡並提出問題。 <br><br> 此外，Microsoft 遵守適用於資料處理者的所有其他 GDPR 義務，包括但不限於提供資料保護影響評估和記錄保存。 <br><br> Microsoft 在處理個人資料以供合法的商務作業使用時，會善盡資料控制者適用的 GDPR 義務。 |  |

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
