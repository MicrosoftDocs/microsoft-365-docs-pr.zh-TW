---
title: 適用於 GDPR 的 Windows 企業版 DPIA 資料處理者服務
description: 在使用 Microsoft 企業版的 Windows 資料處理者服務時，尋找相關資訊以判斷是否需要資料保護影響評估 (DPIA)。
keywords: DPIA, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: df294d75f1175684751cefb65bbe52b13c47fc34
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416687"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-data-processor-service-for-windows-enterprise"></a>資料保護影響評估：給使用 Microsoft 企業版的 Windows 資料處理者服務之資料控制器的指引

>[!NOTE]
>本主題適用於 Windows 企業版預覽計畫的資料處理者服務中的參與者，且需要接受特定使用條款。 若要深入了解該計畫並同意使用條款，請參閱 [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview)。

在一般資料保護法規 (GDPR) 規範下，資料控制者需要為「可能導致自然人之權利和自由高風險」的處理作業準備資料保護影響評估 (DPIA)。 Windows 企業版自身的資料處理者服務中沒有任何固有的功能，因此需要使用資料控制器建立 DPIA。 相反地，是否需要 DPIA 會視資料控制器部署、設定及使用 Windows 企業版資料處理者服務的方式而有所不同。 

本文件旨在提供資料控制者有關 Windows 企業版資料處理者服務的資訊，協助他們判斷是否需要 DPIA，以及若需要，應包含哪些詳細資料。

>[!Note]
>Microsoft 在本文件中不提供任何法律建議。 本文件僅供參考。 我們鼓勵客戶與其隱私權主管和法律顧問合作，以確定與使用 Windows 企業版資料處理者服務或其他任何 Microsoft 線上服務相關之任何 DPIA 的必要性和內容。

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>第 1 部分 – 判斷是否需要 DPIA

GDPR 第 35 條規定，「如果某種處理，特別是使用新技術，並考慮到處理的性質、範圍、背景和目的，可能會對自然人的權利和自由造成高度風險」，資料控制者需要建立「資料保護影響評估」(DPIA)。 它會進一步設定表示以下表格所述之高風險的特定因素。 在判斷是否需要 DPIA 時，資料控制器應考慮這些因素，以及任何其他相關因素，並將其用於 Windows 企業版的資料處理者服務的特定執行和使用。

## <a name="table-1--data-processor-service-for-windows-enterprise-dpia-risk-factors"></a>表格 1：Windows 企業版資料處理者服務 DPIA 風險因素 

|||
|:----|:----|
|**高風險因素**|**Windows 企業版資料處理者服務的相關資訊**|
| 基於自動化處理對自然人的個人方面進行系統和廣泛的評估，包括概況分析，以及對自然人產生法律效果的決定或對自然人產生同樣重大影響的決定。 |Windows 企業版資料處理者服務未提供用來執行某些資料自動處理的功能。<br><br> 不過，由於其他服務會使用 Windows 企業版資料處理者服務做為資料來源，資料控制器可能會將這些服務設定為用於處理。 控制器應根據連線到 Windows 企業版資料處理者服務之服務的使用來做出這項決定。|   
| 大規模處理特殊類別的資料 (揭露種族或民族血統、政治傾向、宗教或哲學信仰，或貿易同盟會員資格的個人資料，用於唯一識別自然人的基因資料、計量生物學資料，有關健康的資料或有關自然人性生活或性向的資料)，或與刑事定罪和犯罪行為有關的個人資料。 | Windows 企業版資料處理者服務並非特別設計用來處理特殊類別的個人資料，Windows 企業版資料處理者服務的使用方式並不會增加控制者處理的固有風險。<br><br> 不過，資料控制器可以使用連線至 Windows 企業版資料處理者服務的服務，處理特定類別的資料。 使用 Windows 企業版資料處理者服務做為資料來源的服務可讓客戶追蹤或以其他方式處理任何類型的資料，包括個人資料的特殊類別。 但身為資料處理者，Microsoft 對於這類使用無控制權，且只有少許或完全沒有對該使用的瞭解。 資料控制器擁有權，可決定資料控制器資料的適當使用。 |

## <a name="part-2--contents-of-a-dpia"></a>第 2 部分：DPIA 的內容 

第 35 (7) 條規定「資料保護影響評估」對設想的處理和處理目的進行有系統的描述。完整的 DPIA 系統描述可能包含像是處理的資料類型、資料會保留多久、資料位置和傳輸目的地，以及哪些第三方可以存取資料。此外，DPIA 也必須包含： 

評估與目的有關的處理操作的必要性和比例性； 

評估自然人的權利和自由風險；和  

旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合本條例。 

下表包含與這些元素相關的 Windows 企業版資料處理者服務相關資訊。 在第 1 部分，資料控制器需考慮以下提供之細節，以及任何其他相關因素，並將其用於 Windows 企業版資料處理者服務的特定執行和使用。 

## <a name="table-2--data-processor-service-for-windows-enterprise-dpia-elements"></a>表 2：Windows 企業版 DPIA 風險因素的資料處理者服務 

||||
|:---|:---|:--|
|**DPIA 的要素**|**Windows 企業版資料處理者服務的相關資訊**| |
| 處理的目的 | 使用 Windows 企業版資料處理者服務進行處理診斷資料的目的取決於進行實作、設定及使用的控制者。 <br><br> 根據[線上服務條款 (OST)](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) 的規定，Microsoft 作為資料處理者，處理客戶資料僅為向我們的客戶 (資料控制者) 提供所要求的服務。 Microsoft 不會將客戶資料或任何衍生的資料用於廣告或類似的商業用途。 |
| 處理的個人資料類別 | **客戶資料** - 由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。 客戶資料包含使用者名稱和 Azure Active Directory 中的使用者名稱和連絡人資訊，以及透過 Windows 診斷資料提供的裝置資訊的使用者名稱和連絡人資訊。 <br><br> **系統產生的記錄** - 由 Microsoft 所產生，且協助 Microsoft 向使用者提供企業服務的資料。 系統產生的資料主要包含經過假名化處理的資料，例如唯一識別碼，由系統所產生，無法單獨用來識別個人，但可用來向使用者提供企業服務。 系統產生的資料也可能包含使用者的身分識別資訊 (例如使用者名稱)。 <br><br> **支援資料** - 這是為了獲得線上服務的技術支援，由客戶或代表客戶 (或客戶授權 Microsoft 從線上服務取得) 透過與 Microsoft 的合作向 Microsoft 提供的資料。 <br><br> 如需有關 Windows 企業版資料處理者服務的處理資料詳細資訊，請參閱[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)以及 [Microsoft 信任中心](https://www.microsoft.com/trustcenter)。 |
| 資料保留 | Microsoft 將在客戶使用線上服務的權利期間保留及處理客戶資料，直到客戶擷取資料或根據 OST 條款刪除客戶資料。 在客戶訂閱期間，客戶可隨時匯出儲存在 Windows 企業版資料處理者服務中的客戶資料。 客戶可以使用 [Windows 企業版資料處理者服務資料主體要求 GDPR 文件](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) 中描述的功能，根據資料主體要求刪除個人資料。
| 個人資料的位置和傳輸 | Windows 企業版資料處理者服務的客戶資料位於美國的 Microsoft 資料中心。 |
| 與第三方共用資料 | Microsoft 與充當我們子處理者 (也就是處理個人資料的次承攬人) 的第三方共用資料，以支援客戶、技術支援、服務維護及其他操作等功能。接收 Microsoft 傳輸的客戶資料或支援資料的所有次承攬人，都會與 Microsoft 達成書面協議，提供的保護不低於[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)中的資料保護條款。所有共用客戶資料或支援資料的第三方次承攬人都納入[次承攬人清單](https://www.microsoft.com/trustcenter/privacy/who-can-access-your-data-and-on-what-terms#subcontractors)中 (請參閱「我們限制次承攬人的存取」)。 <br><br> 針對執法機關和第三方對客戶資料和支援資料的要求，Microsoft 回應的相關資訊在線上服務條款中。除非法律禁止 Microsoft 這樣做，Microsoft 會嘗試引導執法機關或第三方直接向客戶提出要求。 |
| 資料主體權利 | 以處理者的身分操作時，Microsoft 會為客戶 (控制者) 提供資料主體的個人資料，及其依據 GDPR 行使其權利時履行資料主體要求的能力。 Microsoft 執行此作業的方式與產品功能一致，且其角色如同是資料處理者。  如果 Microsoft 收到客戶資料主體中的要求，指出想要依據 GDPR 行使其一或多項權利，該要求將會重新導向至資料控制者。 <br><br> [Windows 企業版資料處理者服務資料主體要求 GDPR 文件](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) 中說明如何使用 Windows 企業版資料處理者服務的功能支援資料主體權利。 |
| 評估與目的有關的處理操作的必要性和比例性 | 這類評估取決於資料控制者的需求和處理的目的。 <br><br> 關於 Microsoft 進行的處理，這種處理對於向資料控制者提供服務的目的是必要的且符合比例原則。Microsoft 在 OST 中做出此一承諾。 |
| 評估資料主體的權利和自由風險  | 資料主體使用 Windows 企業版資料處理者服務在權利和自由方面的主要風險，將取決於控制者如何以及在何種情況下實作、設定及使用 Windows 企業版資料處理者服務。 <br><br> 但是，與任何服務一樣，服務中保存的個人資料可能存在未經授權的存取或無意揭露的風險。OST 中討論 Microsoft 為解決這些風險所採取的措施，詳述於下。 |
| 旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合 GDPR。 | Microsoft 致力於幫助保護客戶資料的安全。Microsoft 所採取的安全性措施詳述於 OST 中。<br><br> Microsoft 採取合理且適當的技術和組織措施來保護其所處理的個人資料。 這些措施包括（但不限於）內部隱私政策和做法、合約承諾，以及國際和地區性標準認證。 如需詳細資訊，請移至 [信賴中心的隱私權標準頁面](https://www.microsoft.com/trustcenter/privacy/we-set-and-adhere-to-stringent-standards)。 <br><br> Microsoft 提供重要、透明的面向客戶的安全性和隱私權材料，以幫助解釋 Microsoft 對個人資料的使用和處理。我們歡迎客戶連絡 Microsoft 提出問題。 <br><br> 此外，Microsoft 遵守適用於資料處理者的所有其他 GDPR 義務，包括但不限於提供資料保護影響評估和記錄保存。| 
