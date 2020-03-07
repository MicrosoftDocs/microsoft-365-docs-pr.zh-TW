---
title: GDPR 和 CCPA 的 Dynamics 365 資料主體要求
description: 本指南會介紹如何使用 Microsoft 產品、服務及系統管理工具，協助我們的控制者客戶找出並處理個人資料，以回應 DSR 和 CCPA 要求。
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: 38c50703fbc58e85a646720b5bbe8b400477b9d4
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558003"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的 Dynamics 365 資料主體要求

歐盟[一般資料保護規定 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 賦予人員 (在規範中稱為「資料主體」**) 權限，以管理由雇主或其他類型的公司或組織 (稱為「資料控制者」** 或簡稱「控制者」**) 收集而來的個人資料。個人資料在 GDPR 中的定義非常廣泛，係指與已識別或可識別自然人相關的任何資料。GDPR 賦予資料主體對其個人資料的特定權限，這些權限包括取得個人資料副本、要求更正資料、限制資料的處理、刪除資料或以電子格式接收資料，以便轉交給其他控制者。由資料主體向控制者提出對其個人資料採取某項動作的正式要求，稱為「資料主體要求」或 DSR**。

同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。  CCPA 也提供特定接露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。 銷售的廣泛定義，包括出於有價值的考量而共用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

本指南會討論如何使用 Microsoft 產品、服務及系統管理工具，協助我們的控制者客戶找出並處理個人資料，以回應 DSR 要求。 具體而言，這包括如何尋找、存取和處理位於 Microsoft 雲端的個人資料或個人資訊。 以下是本指南中所述程序的快速概觀：

- **探索**：使用搜尋和探索工具，更輕鬆地尋找可能成為 DSR 要求主體的客戶資料。 收集到可能的回應文件之後，您就可以執行下列步驟中所述的一或多個 DSR 動作來回應要求。 或者，您可能判定該要求不符合組織回應 DSR 要求的方針。
- **存取：** 擷取在 Microsoft 雲端中常駐的個人資料，若有要求，請製作可供資料主體使用的副本。
- **修正：** 在適用情況下，對個人資料進行變更或實行其他要求的動作。
- **限制：** 藉由盡可能移除各種線上服務的授權或關閉所需的服務，以限制個人資料的處理。 您可以
- **刪除：** 永久移除 Microsoft 雲端中常駐的個人資料。
- **匯出/接收 (可攜性)：** 將個人資料或個人資訊以電子複本 (以電腦可讀取的格式) 提供給資料主體。 CCPA 中的個人資訊是任何與已識別或可識別個人相關的資訊。 個人的私人、公開或公司角色之間沒有區別。 定義的「個人資訊」一詞在 GDPR 下，大致與「個人資料」相符。 不過，CCPA 也包含家庭和家用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

本指南中的每一節概述資料控制者組織可以採取的技術程序，以回應對 Microsoft 雲端中個人資料的 DSR 要求

### <a name="gdpr-terminology"></a>GDPR 詞彙

以下提供與本指南相關的詞彙定義：

- **控制者：** 自然人或法人、公家機關、公司或其他主體，不論單獨或與其他單位聯合，會判斷處理個人資料的用途以及方式，其中此類處理的用途以及方式的判斷是根據聯盟與成員國法律，控制者人選或提名控制者的特定準則可由聯盟與成員國法律提供。
- **個人資料和資料主體：** 表示與已識別或可識別之自然人 (以下稱為「資料主體」) 相關的任何資訊；可識別的自然人是可以直接或間接識別的人員，尤其是藉由參照如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身分等一個或多個識別碼來識別。
- **處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。
- **客戶資料：** 由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。 客戶資料包括 (1) 使用者的識別資訊 (例如 Azure Active Directory 中的使用者名稱和連絡人資訊)，以及客戶上傳到特定服務或在特定服務中建立的客戶內容 (例如，Azure 儲存體帳戶中的客戶內容、Azure SQL Database 的客戶內容，或 Azure 虛擬機器中客戶的虛擬機器映像)。
- **系統產生的記錄：** Microsoft 產生的記錄及相關資料，可協助 Microsoft 向使用者提供企業服務。 系統產生的記錄主要包含經過假名化處理的資料 (例如唯一識別碼)，一般是由系統所產生的數字，無法單獨用來識別個人，但可用來向使用者提供企業服務。 系統產生的記錄也可能包含使用者的身分識別資訊 (例如使用者名稱)。

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>本指南如何協助您符合您的控制者責任

本指南分為兩個部分，說明如何使用 Dynamics 365 產品、服務及系統管理工具，協助您找出Microsoft 雲端中的資料並對其採取動作，以回應根據 GDPR 行使其權利的資料主體的要求。 第一部分介紹客戶資料中包含的個人資料，第二部分介紹在系統產生記錄中擷取的其他假名化個人資料。

- **第 1 部分：針對對客戶資料中包含的個人資料，回應資料主體權利 (DSR) 要求：** 本指南中的第 1 部分將討論如何存取、修正、限制、刪除個人資料，並將其從 Dynamics 365 應用程式 (軟體即服務) 中匯出；系統會將其當作您提供給線上服務的客戶資料中的一部分來處理。
- **第 2 部分：回應假名化資料的資料主體權利要求：** 當您使用 Dynamics 365 企業服務時，Microsoft 會產生一些資訊 (亦即本文件內的*系統產生的記錄*) 以提供服務，此資訊僅限於使用者留下而可識別他們在系統中動作的使用記錄。 在未使用其他資訊的情況下，雖然無法將這項資料歸屬於特定資料主體，但其中有部分在 GDPR 的規範下，仍可能會視為屬於個人資料。 本指南第 2 部分會討論如何存取、刪除及匯入由 Dynamics 365 所產生之系統產生的記錄。

### <a name="preparing-for-data-subject-rights-investigations"></a>準備資料主體權限調查

當資料主體行使其權利並提出要求時，請考慮下列重點：

- 使用資料主體在要求過程中所提供的資訊，適當地識別人員與角色 (例如員工、客戶、供應商)。 這項資訊可能是名稱、員工識別碼或客戶編號或其他識別碼。
- 記錄該要求的資料及時間。(您有 30 天的時間可以完成該要求)。
- 確認要求符合貴組織的需求，以便接受或拒絕資料主體的要求。例如，您必須確保執行要求不會與任何其他法律、財務或您負有的義務相衝突，或影響他人的權利和自由。
- 請確認您擁有與要求相關的資訊。

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>第 1 部分：回應客戶資料中所包含個人資料的資料主體權限要求

在下列文章中，您會找到資訊可協助您針對在 Dynamics 365 中所處理的客戶資料內包含的個人資料，以準備好並回應 DSR 要求。請務必注意，在服務線上服務訂用帳戶的過程中，Microsoft 處理的其他類別資料中可能會出現個人資料 (例如 Microsoft 隱私權聲明中所定義的系統管理員資料或支援資料)。這份文件僅限於在探索及管理 DSR 要求程序上提供協助，該 DSR 要求會影響您提供給 Dynamics 365 的客戶資料中所存在的個人資料。

Dynamics 365 是種以軟體為服務 (SaaS) 的形式提供多重資料處理功能的線上服務。因此，Dynamics 365 提供的各種功能適用於處理各種資料集合，這些集合在性質、用途或其他特定屬性 (例如銷售資料、交易、財務、人力資源資訊等) 方面都非常不同。因為這項差異，Dynamics 365 會提供數個表單、欄位、結構描述、端點和邏輯以處理客戶資料；這也反映在每個應用程式中會有數個處理 DSR 要求的方式上。若 Dynamics 365 應用程式提供幾種解決特定 DSR 要求的方式，我們會備註在本指南中，指出每個應用程式所提供的技術描述。

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>尋找客戶資料

回應資料主體權限要求的第一個步驟是搜尋並找出該要求主體的客戶資料。

適當地將客戶資料分類是在 Dynamics 365 Customer Engagement 商務應用程式中處理個人資料的核心概念。Dynamics 365 for Customer Engagement 可讓您根據資料分類靈活地建置應用程式擴充功能。適當的分類可讓您識別出哪些資訊是個人資料，讓您在回應來自資料主體的要求時，可找出並擷取資料。此也有助於符合適用於收集及管理個人資料的法律及法規需求。

Microsoft 提供有助於回應資料主體權利要求的功能，並可用以存取客戶資料。不過，您有責任確保能適當找出並分類個人資料。

***Dynamics 365 for Customer Engagement*** 提供多種方法 (例如：進階尋找搜尋和搜尋記錄)，讓您搜尋記錄中的個人資料。 這些功能都可讓您識別 (找出) 個人資料。

- [進階尋找搜尋](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- 可跨多種記錄類型[搜尋記錄](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records)

在 Dynamics 365 for Marketing 中，您還可以：

1. [建置 Power BI 報表](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm)以篩選並識別客戶資料。
2. 利用對連絡人和行銷執行物件的深入了解檢視，找出可能包含客戶資料的其他資料點。

***Dynamics 365 Customer Service Insights*** 提供的資源清單可協助您[尋找客戶資料](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery)以便回應來自客戶的 GDPR 要求。 

***Dynamics 365 for Finance and Operations*** 提供數個方式讓您搜尋客戶資料。 身為租用戶系統管理員的您，可以執行下列動作來搜尋客戶資料：

- 透過可快速探索個人資料的方法整理客戶資料，請參閱[如何分類資料庫存](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory)以達成此目的。
- 使用[人員搜尋報表](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report)來找出並收集個人資料。
- 透過撰寫新實體或擴充現有的實體，來[擴充人員搜尋報表](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)。
- 使用搜尋和篩選功能來尋找特定個人資料，並使用 Microsoft Office 匯出功能將該資料匯出，或使用瀏覽器延伸將該資訊列印為 .pdf 檔。
- 撰寫可找出並匯出個人資料的自訂表單。
- 撰寫外部入口網站或網站，讓已驗證的客戶查看他/她的個人資料。

***Dynamics 365 Business Central*** 提供數個方式讓您搜尋客戶資料。 如需詳細資訊，請參閱[搜尋、篩選及排序資料](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters)。

***Dynamics 365 for Talent*** 提供可尋找特定個人資料的進階搜尋和篩選功能，以及可匯出該資訊或使用瀏覽器擴充將該資訊列印為 .pdf 檔的 Microsoft Office 匯出功能。

- 使用[人員搜尋報表](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report)來找出並收集客戶資料。
- 透過撰寫新實體或擴充現有的實體，來[擴充人員搜尋報表](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)。

### <a name="providing-a-copy-of-customer-data"></a>提供客戶資料的副本

***Dynamics 365 for Customer Engagement*** 中的客戶資料可使用完整的實體匯出功能來匯出。 客戶資料可以匯出為靜態 Excel 檔案，以利資料可攜性要求。 之後您可以使用 Excel 來編輯要包含在可攜性要求中的個人資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 透過[常見資料服務 Web API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/overview) 可以匯出 Dynamics 365 for Customer Engagement 記錄。

此外，針對 Dynamics 365 for Marketing，系統會提供[專用的 API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact)，讓客戶可建置擴充功能，以便從已擷取的客戶互動中，擷取可能內含個人資料的其他記錄。該 API 會載入後端系統中的所有相關資訊，並將其組合成單一的可攜式文件。

***Dynamics 365 Customer Service Insights*** 可讓您使用資料匯出來[提供客戶資料的副本](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)。

***Dynamics 365 for Finance and Operations*** 中的客戶資料可使用完整的實體匯出功能來匯出。 使用[*資料管理與整合實體*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)，租用戶系統管理員可以利用提供的實體、建立新實體或延伸現有、可重複的個人資料的實體，使用[*資料匯入及匯出工作*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)匯出至 Excel 或許多其他常見格式。  另一方面，許多清單可以匯出為靜態 Excel 檔案，以利資料可攜性要求。 將客戶資料匯出至 Excel 後，之後您可以編輯要包含在可攜性要求中的個人資料，然後將檔案儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 您也可以考慮使用「人員搜尋報告」來提供您已分類為個人資料之資料的資料主題。

在 ***Dynamics 365 Business Central*** 中，您可以使用兩種功能將客戶資料的副本提供給資料主體：

您可以將客戶資料匯出為 Excel 檔案。 之後您可以在 Excel 中編輯要包含在可攜性要求中的客戶資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 如需詳細資訊，請參閱[將您的商務資料匯出至 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。

在 ***Dynamics 365 for Talent*** 中，您可以使用[擴充人員搜尋報表](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)，來蒐集資訊以支援對資料主體之個人資料副本的要求。

### <a name="rectifying-customer-data"></a>修正客戶資料

***Dynamics 365 for Customer Engagement*** 提供您以下方法來修正不精準或不完整的客戶資料，或清除客戶資料：

- 使用「尋找客戶資料」中所述的功能來搜尋客戶資料，並在 Customer Engagement Forms 中直接編輯資料。 您可在單一資料列層級進行編輯，或直接修改多個資料列。
- 大量編輯多個 Customer Engagement 記錄：您可以利用 Microsoft Office 增益集將資料匯出至 Microsoft Excel、進行變更，然後將已修改的資料從 Excel 匯入至 Dynamics 365 for Customer Engagement。

此外，針對 Dynamics 365 for Marketing，您還可以：

- 藉由直接編輯單一或多個資料列，更新我的資料登陸頁面
- 準備 [[訂閱中心]](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) 頁面，其中含有多個可包含的可編輯連絡人欄位。

***Dynamics 365 Customer Service Insights*** 也提供讓組織[改正或變更客戶資料](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary)的功能。

在 ***Dynamics 365 for Finance and Operations*** 中，您也可以使用[*自訂工具*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)，但須由您負責決策及實作。

***Dynamics 365 Business Central*** 提供兩個方法來修正不精準或不完整的客戶資料。

若要快速大量編輯 Business Central 的多筆記錄，您可以使用 [Business Central Excel 增益集](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in)將清單匯出至 Excel 來修正多筆記錄，然後再從 Business Central 中的 Excel 發佈已修改的資料。如需詳細資訊，請參閱[將您的商務資料匯出至 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。

您可以手動編輯內含目標個人資料的資料元素，來變更在任何欄位中所儲存的客戶資料 (例如客戶卡片中客戶的相關資訊)。 如需詳細資訊，請參閱[輸入資料](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)。

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>修改商務交易中項目的簡短備註

交易記錄 (例如一般、客戶和稅務會計項目) 是企業資源規劃系統不可或缺的部分。屬於財務或其他交易的個人資料會維持「現況」以遵守財務法規 (例如，稅法)、防止詐騙 (例如安全性稽核記錄)，或遵守產業認證。因此，Dynamics 365 for Finance and Operations 和 Dynamics 365 Business Central 會限制對這類記錄中資料的修改。

如果您在商務交易記錄中儲存個人資料，更正、刪除或限制處理個人資料以接受資料主體請求的唯一方法是使用 Dynamics 365 Business Central [自訂功能](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index)。[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)是否接受資料主體的修改要求並付諸實行，需由您自行決定。

### <a name="restricting-the-processing-of-customer-data"></a>限制處理客戶資料

當您從資料主體收到限制對客戶資料處理的要求時，可輕易從線上服務擷取受影響的客戶資料，並將其儲存在個別容器 (即，內部部署儲存空間或具有資料隔離功能的個別 Web 服務) 中，與任何雲端應用程式所提供的處理功能隔離。

替代機制，例如資料處理封鎖是由 ***Dynamics 365 Business Central*** 提供，在其中，使用者能夠封鎖特定資料主體的記錄。 如需詳細資訊，請參閱[限制資料主體的資料處理](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject)。 當記錄標示為已封鎖時，Dynamics 365 Business Central 將不再繼續處理該資料主體的客戶資料。 您無法建立使用封鎖的記錄的新交易。比方說，當客戶或銷售人員遭封鎖時，您無法為客戶建立新發票。

### <a name="deleting-customer-data"></a>刪除客戶資料

當資料主體要求您刪除其客戶資料時，有數個方式可以執行這項操作：

- 大量編輯多個 Dynamics 365 記錄，您可以利用 Microsoft Office 增益集將資料匯出至 Microsoft Excel、進行變更，然後將已修改資料從 Excel 匯入至線上服務。
- 您可以找出您想要刪除的資料，來刪除在任何欄位中儲存的客戶資料，然後手動刪除內含目標客戶資料的資料元素 (就像對代表資料主題的連絡人記錄與包含個人資料的其它記錄使用實刪除)

此外，針對 Dynamics 365 Marketing，刪除連絡人將確保也會移除具有個人資訊的互動資料。 若為任何自訂欄位或實體，您必須自訂您的系統，以確定會從相關記錄中刪除所有客戶資料和/或從連絡人記錄中取消連結，以便移除所有個人資訊。 詳細資訊：[開發人員指南 (行銷)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide)。

***Dynamics 365 Customer Service Insights*** 也提供讓組織[刪除客戶資料](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete)的功能。

或者，您也可以在 ***Dynamics 365 for Finance and Operations*** 中使用[*自訂工具*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)來清除/修改客戶資料。

在 ***Dynamics 365 Business Central*** 中，當資料主體要求您刪除剛好包含在您的客戶資料中的個人資料時，有數個方法可以解決此要求：

- 若要快速大量編輯 Business Central 的多筆記錄，您可以使用 [Business Central Excel 增益集](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in)來刪除多筆記錄，然後再從 Business Central 中的 Excel 發佈這些變更。如需詳細資訊，請參閱[將您的商務資料匯出至 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。
- 您可以手動刪除包含目標客戶資料的資料元素，來刪除儲存在任何欄位中的客戶資料。 如需詳細資訊，請參閱[輸入資料](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)。
- 例如，您可以刪除連絡人，然後執行「刪除已取消的互動記錄項目」批次作業來直接刪除客戶資料，以刪除與該連絡人的互動。
- 您可以[刪除包含客戶資料的文件](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents)，例如備忘錄和已過帳的銷售和採購發票。

除了大量或單獨刪除個別記錄，請注意，只有已離職的員工可以從 ***Dynamics 365 for Talent*** 完整刪除。[請按照這些步驟來刪除已離職的員工](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data)。

### <a name="exporting-customer-data"></a>匯出客戶資料

為了回應資料可攜性要求，***Dynamics 365 for Customer Engagement*** 中的客戶資料可使用完整的實體匯出功能來匯出。 客戶資料可以匯出為靜態 Excel 檔案，以利資料可攜性要求。 之後您可以使用 Excel 來編輯要包含在可攜性要求中的個人資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。

此外，針對 Dynamics 365 for Marketing，系統會提供[專用的 API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact)，讓客戶可建置擴充功能，以便從已擷取的客戶互動中，擷取可能內含個人資料的其他記錄。該 API 會載入後端系統中的所有相關資訊，並將其組合成單一的可攜式文件。

針對 ***Dynamics 365 Customer Service Insights***，您可以透過 Azure 管理入口網站[匯出客戶資料](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)。

***Dynamics 365 for Finance and Operations*** 提供[資料管理與整合實體](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)，它使得提供的實體、新建立的實體，或延伸可重複的個人資料的實體，能夠使用[資料匯入和匯出作業](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)匯出至 Excel 或許多其他常見格式。  另一方面，許多清單可以匯出為靜態 Excel 檔案，以利資料可攜性要求。 以此方式將客戶資料匯出至 Excel 後，之後您可以編輯要包含在可攜性要求中的個人資料，然後將檔案儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。

Dynamics 365 for Finance and Operations 和 ***Dynamics 365 for Talent*** 兩者都提供了 [人員搜尋報表]，可將已分類為個人資料的資料提供給資料主體。 

***Dynamics 365 Business Central*** 提供下列功能：

- 您可以將客戶資料匯出為 Excel 檔案。 之後您可以在 Excel 中編輯要包含在可攜性要求中的客戶資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 如需詳細資訊，請參閱[將您的商務資料匯出至 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。
- 您可以將客戶資料匯出為 Excel 檔案。 之後您可以在 Excel 中編輯要包含在可攜性要求中的客戶資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 如需詳細資訊，請參閱[將您的商務資料匯出至 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>第 2 部分：回應系統所產生記錄的 DSR

Microsoft 也讓您能夠存取、匯出及刪除系統產生的記錄檔，根據 GDPR「個人資料」的廣泛定義，這些記錄可能會視為個人資料。系統產生的記錄檔中，根據 GDPR可能會視為個人資料的範例包括：

- 產品和服務使用情況資料 (例如使用者活動記錄)
- 使用者搜尋要求和查詢資料
- 作為系統功能與使用者或其他系統互動的產品和服務所產生的資料

請注意，系統不支援在系統產生的記錄中限制或修正資料的能力。系統所產生的記錄構成了 Microsoft 雲端中所進行的實際動作和診斷資料，對這類資料的修改會危害動作的歷程記錄，並增加詐騙和安全性風險。

### <a name="accessing-and-exporting-system-generated-logs"></a>存取和匯出系統所產生的記錄

系統管理員可以存取與特定使用者的 Dynamics 365 服務與應用程式相關聯、並由系統產生的記錄檔。若要存取並匯出系統產生的記錄檔：

1. 請移至 [Microsoft 服務信任入口網站](https://servicetrust.microsoft.com/)，並使用 Dynamics 365 全域系統管理員認證登入。
2. 在頁面頂端的 [隱私權]**** 下拉式清單中，按一下 [資料主體要求]****。
3. 在 [資料主體要求]**** 頁面的 [系統產生的記錄]**** 底下，按一下 [資料記錄匯出]****。
    > [!NOTE]
    > [資料記錄匯出]**** 頁面隨即出現。請注意，系統會顯示一份貴組織所提交的匯出資料要求清單。
4. 若要為某個使用者新建要求，請按一下 [建立匯出資料要求]****。

建立新要求後，該要求會列在 [資料記錄檔匯出] **** 頁面上，您可在其中追蹤其狀態。要求完成後，您可以按一下連結來存取系統產生的記錄檔，系統會在該要求建立後 30 天內，將此記錄檔匯出至貴組織的 Azure 儲存位置。系統將以常見、機器可讀取的檔案格式 (例如 JSON 或 XML) 來儲存資料。如果您沒有 Azure 帳戶和 Azure 儲存位置，就必須為貴組織建立 Azure 帳戶和/或 Azure 儲存位置，讓「資料記錄檔匯出」工具可以匯出系統產生的記錄檔。

Azure 可支援這點；我們讓貴組織能以原生 JSON 格式，將資料匯出到您指定的Azure 儲存體容器。[Microsoft Azure 儲存體 - Blob 儲存體簡介](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage)一文。

> [!IMPORTANT]
> 您必須是租用戶系統管理員，才能從租用戶中匯出使用者資料。

下表摘要列出系統所產生記錄檔的存取和匯出：

| | |
|:----|:---|
| | |
|**Microsoft 資料記錄檔匯出工具需要花費多少時間才能完成要求？**| 這取決於數項因素；在大多數情況下，一或兩天應可完成，但也有可能需要最長 30 天的時間。 |
|**輸出的格式是什麼？**| 輸出會是機器可讀取的結構化檔案，例如 XML、CSV 或 JSON。 |
|**資料記錄檔匯出工具傳回的資料為何？**| 資料記錄匯出工具會傳回 Microsoft 儲存的系統產生的記錄檔。 匯出的資料會跨越不同的 Microsoft 服務，包括 Office 365、Azure 和 Dynamics。 |
|***誰有權存取資料記錄檔匯出工具，以提交對系統所產生記錄檔的存取要求？**| Dynamics 365 全域系統管理員將有權存取「GDPR 記錄檔管理員」公用程式。 |
|**資料傳回給使用者的方式為何？**| 系統會將資料匯出至貴組織的 Azure 儲存體位置；貴組織的系統管理員將決定是否向使用者顯示此資料，或將此資料傳回給使用者。 |
|**資料在系統產生的記錄檔中看起來會是麼樣子？**| 以 JSON 格式記錄的系統所產生記錄檔範例： <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

> [!NOTE]
> 基於安全性和稽核理由，部分功能不允許匯出或刪除含個人資訊的系統所產生記錄，以維持這些資訊的完整性。

### <a name="deleting-system-generated-logs"></a>刪除系統產生的記錄

若要透過存取要求來刪除系統產生的記錄檔，您必須將使用者從該服務中移除，並永久刪除其 Azure Active Directory 帳戶。如需永久刪除使用者的相關指示，請參閱本指南中[刪除使用者](https://microsoft-my.sharepoint.com/personal/kated_microsoft_com/Documents/DSR%20Guide%20v4%20-(newly%20created%20for%20O365%20only).docx#_Deleting_a_user)一節。請務必注意，一旦開始永久刪除使用者帳戶即無法復原。

永久刪除使用者帳戶會在 30 天內將使用者資料，從幾乎所有 Dynamics 365 服務的系統產生的記錄中移除。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
