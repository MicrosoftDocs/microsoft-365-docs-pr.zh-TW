---
title: 適用于 Windows 的 DPIA 資料處理程式服務 GDPR
description: 在使用 Microsoft 的 Windows 資料處理程式服務時，尋找相關資訊以判斷是否需要資料保護影響評估 (DPIA)。
keywords: DPIA, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: c594bbca6383874346719a477d3f86f3dac99409
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023601"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-data-processor-service-for-windows"></a>資料保護影響評估：給使用 Microsoft 的 Windows 資料處理程式服務之資料控制器的指引

>[!NOTE]
>本主題適用於 Windows 預覽計畫的資料處理者服務中的參與者，且需要接受特定使用條款。 若要深入了解該計畫並同意使用條款，請參閱 [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview)。

在一般資料保護法規 (GDPR) 規範下，資料控制者需要為「可能導致自然人之權利和自由高風險」的處理作業準備資料保護影響評估 (DPIA)。 Windows 自身的資料處理程式服務中沒有任何固有的功能，因此需要使用資料控制器建立 DPIA。 相反地，是否需要 DPIA 會視資料控制器部署、設定及使用 Windows 版資料處理器服務的方式而有所不同。 

本文件旨在提供資料控制者有關 Windows 資料處理程式服務的資訊，協助他們判斷是否需要 DPIA，以及若需要，應包含哪些詳細資料。

>[!Note]
>Microsoft 在本文件中不提供任何法律建議。 本文件僅供參考。 我們鼓勵客戶與其隱私權主管和法律顧問合作，以確定與使用 Windows 資料處理程式服務或其他任何 Microsoft 線上服務相關之任何 DPIA 的必要性和內容。

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>第 1 部分 – 判斷是否需要 DPIA

GDPR 第 35 條規定，「如果某種處理，特別是使用新技術，並考慮到處理的性質、範圍、背景和目的，可能會對自然人的權利和自由造成高度風險」，資料控制者需要建立「資料保護影響評估」(DPIA)。 它會進一步設定表示以下表格所述之高風險的特定因素。 在判斷是否需要 DPIA 時，資料控制器應考慮這些因素，以及任何其他相關因素，並將其用於 Windows 的資料處理器服務的特定執行和使用。

## <a name="table-1--data-processor-service-for-windows-dpia-risk-factors"></a>表格1： Windows 版資料處理器服務 DPIA 風險因素 

|||
|:----|:----|
|**高風險因素**|**Windows 版資料處理器服務相關資訊**|
| 基於自動化處理對自然人的個人方面進行系統和廣泛的評估，包括概況分析，以及對自然人產生法律效果的決定或對自然人產生同樣重大影響的決定。 |Windows 資料處理程式服務未提供用來執行某些資料自動處理的功能。<br><br> 不過，由於其他服務會使用 Windows 版資料處理器服務做為資料來源，資料控制器可能會將這些服務設定為用於處理。 控制器應根據連線到 Windows 資料處理器服務之服務的使用來做出這項決定。|   
| 大規模處理特殊類別的資料 (揭露種族或民族血統、政治傾向、宗教或哲學信仰、或貿易同盟會員資格的個人資料，用於唯一識別自然人的基因資料、計量生物學資料，有關健康的資料或有關自然人性生活或性向的資料)，或與刑事定罪和犯罪行為有關的個人資料。 | Windows 資料處理程式服務並非特別設計用來處理特殊類別的個人資料，Windows 資料處理程式服務的使用方式並不會增加控制者處理的固有的風險。<br><br> 不過，資料控制器可以使用連線至 Windows 資料處理器服務的服務，處理特定類別的資料。 使用 Windows 版資料處理器服務做為資料來源的服務可讓客戶追蹤或以其他方式處理任何類型的資料，包括個人資料的特殊類別。 但身為資料處理者，Microsoft 對於這類使用無控制權，且只有少許或完全沒有對該使用的瞭解。 資料控制器擁有權，可決定資料控制器資料的適當使用。 |

## <a name="part-2--contents-of-a-dpia"></a>第 2 部分：DPIA 的內容 

Article 35(7) mandates that a Data Protection Impact Assessment specify the purposes of processing and a systematic description of the envisioned processing. A systematic description of a comprehensive DPIA might include factors such as the types of data processed, how long data is retained, where the data is located and transferred, and what third parties may have access to the data. In addition, the DPIA must include: 

評估與目的有關的處理操作的必要性和比例性； 

評估自然人的權利和自由風險；和  

旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合本條例。 

下表包含與這些元素相關的 Windows 資料處理器服務相關資訊。 在第一部分，資料控制器需考慮以下提供之細節，以及任何其他相關因素，並將其用於 Windows 的資料處理器服務的特定執行和使用。 

## <a name="table-2--data-processor-service-for-windows-dpia-elements"></a>表2 - Windows DPIA 要素的資料處理程式服務 

||||
|:---|:---|:--|
|**DPIA 的要素**|**Windows 資料處理程式服務的相關資訊**| |
| 處理的目的 | 使用 Windows 資料處理程式服務進行處理診斷資料的目的取決於進行實作、設定及使用的控制者。 <br><br> 根據[線上服務條款 (OST)](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) 的規定，Microsoft 作為資料處理者，處理客戶資料僅為向我們的客戶 (資料控制者) 提供所要求的服務。 Microsoft 不會將客戶資料或任何衍生的資料用於廣告或類似的商業用途。 |
| 處理的個人資料類別 | **客戶資料** - 由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。 客戶資料包含使用者名稱和 Azure Active Directory 中的使用者名稱和連絡人資訊，以及透過 Windows 診斷資料提供的裝置資訊的使用者名稱和連絡人資訊。 <br><br> **系統產生的記錄** - 由 Microsoft 所產生，且協助 Microsoft 向使用者提供企業服務的資料。 系統產生的資料主要包含經過假名化處理的資料，例如唯一識別碼，由系統所產生，無法單獨用來識別個人，但可用來向使用者提供企業服務。 系統產生的資料也可能包含使用者的身分識別資訊 (例如使用者名稱)。 <br><br> **支援資料** - 這是為了獲得線上服務的技術支援，由客戶或代表客戶 (或客戶授權 Microsoft 從線上服務取得) 透過與 Microsoft 的合作向 Microsoft 提供的資料。 <br><br> 如需有關 Windows 資料處理程式服務的處理資料詳細資訊，請參閱[線上服務條款](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)以及[Microsoft 信任中心](https://www.microsoft.com/trustcenter)。 |
| 資料保留 | Microsoft 將在客戶使用線上服務的權利期間保留及處理客戶資料，直到客戶擷取資料或根據 OST 條款刪除客戶資料。 在客戶訂閱期間，客戶可隨時匯出儲存在 Windows 資料處理程式服務中的客戶資料。 客戶可以使用 [ Windows 資料處理程式服務資料主體要求 GDPR 文件](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)中描述的功能，根據資料主體要求刪除個人資料。
| 個人資料的位置和傳輸 | Windows 客戶資料的資料處理程式服務位於美國的 Microsoft 資料中心。 |
| 與第三方共用資料 | Microsoft shares data with third parties acting as our subprocessors (i.e., subcontractors which process personal data) to support functions such as customer and technical support, service maintenance, and other operations. Any subcontractors to which Microsoft transfers Customer Data or Support Data will have entered into written agreements with Microsoft that are no less protective than the Data Protection Terms of the [Online Services Terms](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46). All third-party subcontractors with which Customer Data or Support Data is shared are included in the [Lists of subcontractors](https://www.microsoft.com/trustcenter/privacy/who-can-access-your-data-and-on-what-terms#subcontractors) (see “We limit access by subprocessors”). <br><br> Information regarding Microsoft’s response to law enforcement and third party requests for Customer Data and Support Data is located in the Online Services Terms. Unless Microsoft is legally prohibited from doing so, Microsoft will attempt to redirect the law enforcement agency or third party directly to the Customer. |
| 資料主體權利 | 以處理者的身分操作時，Microsoft 會為客戶 (控制者) 提供資料主體的個人資料，及其依據 GDPR 行使其權利時履行資料主體要求的能力。 Microsoft 執行此作業的方式與產品功能一致，且其角色如同是資料處理者。  如果 Microsoft 收到客戶資料主體中的要求，指出想要依據 GDPR 行使其一或多項權利，該要求將會重新導向至資料控制者。 <br><br> [Windows 資料處理程式服務資料主體要求 GDPR 文件](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)中說明如何使用 Windows 資料處理程式服務的功能支援資料主題權利。 |
| 評估與目的有關的處理操作的必要性和比例性 | 這類評估取決於資料控制者的需求和處理的目的。 <br><br> With regard to the processing carried out by Microsoft, such processing is necessary and proportional for the purpose of providing the services to the data controller. Microsoft makes this commitment in the OST. |
| 評估資料主體的權利和自由風險  | 資料主體使用 Windows 資料處理程式服務在權利和自由方面的主要風險將取決於控制者如何以及在何種情況下實作、設定及使用 Windows 資料處理程式服務。 <br><br> However, as with any service, personal data held in the service may be at risk of unauthorized access or inadvertent disclosure. Measures Microsoft takes to address such risks are discussed in the OST, as further detailed below. |
| 旨在解決風險的措施，包括保障措施、安全措施和機制，以確保保護個人資料，並在考慮到資料主體和其他有關人員的權利和合法利益的情況下證明符合 GDPR。 | Microsoft is committed to helping protect the security of Customer Data. The security measures Microsoft takes are described in detail in the OST. <br><br> Microsoft 採取合理且適當的技術和組織措施來保護其所處理的個人資料。 這些措施包括（但不限於）內部隱私政策和做法、合約承諾，以及國際和地區性標準認證。 如需詳細資訊，請移至 [信賴中心的隱私權標準頁面](https://www.microsoft.com/trustcenter/privacy/we-set-and-adhere-to-stringent-standards)。 <br><br> Microsoft provides significant, transparent customer facing security and privacy materials to help explain Microsoft’s use and processing of personal data. Customers are encouraged to contact Microsoft with questions. <br><br> 此外，Microsoft 遵守適用於資料處理者的所有其他 GDPR 義務，包括但不限於提供資料保護影響評估和記錄保存。| 
