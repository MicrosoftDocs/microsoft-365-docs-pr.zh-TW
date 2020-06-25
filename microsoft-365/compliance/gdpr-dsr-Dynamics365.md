---
title: GDPR 和 CCPA 的 Dynamics 365 資料主體要求
description: 了解如何尋找及處理個人資料，以及回應 Dynamics 365 客戶提出的 DSR 和 CCPA 要求。
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
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 04ecbd6e52a56ea83f3b2e2eaebd02de20cfbe52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817662"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的 Dynamics 365 資料主體要求

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called in this document a *Data Subject Rights Request* or DSR request.

同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。  CCPA 也提供特定揭露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。 銷售的廣泛定義，包括出於有價值的考量而共用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

本指南會討論如何使用 Microsoft 產品、服務及系統管理工具，協助我們的控制者客戶找出並處理個人資料，以回應 DSR 要求。 具體而言，這包括如何尋找、存取和處理位於 Microsoft 雲端的個人資料或個人資訊。 以下是本指南中所述程序的快速概觀：

- **探索**：使用搜尋和探索工具，更輕鬆地尋找可能成為 DSR 要求主體的客戶資料。 收集到可能的回應文件之後，您就可以執行下列步驟中所述的一或多個 DSR 動作來回應要求。 或者，您可能判定該要求不符合組織回應 DSR 要求的方針。
- **存取：** 擷取在 Microsoft 雲端中常駐的個人資料，若有要求，請製作可供資料主體使用的副本。
- **修正：** 在適用情況下，對個人資料進行變更或實行其他要求的動作。
- **限制：** 藉由盡可能移除各種線上服務的授權或關閉所需的服務，以限制個人資料的處理。 您可以
- **刪除：** 永久移除 Microsoft 雲端中常駐的個人資料。
- **匯出/接收 (可攜性)：** 將個人資料或個人資訊以電子複本 (以電腦可讀取的格式) 提供給資料主體。 CCPA 中的個人資訊是任何與已識別或可識別個人相關的資訊。 個人的私人、公開或工作角色之間沒有區別。 定義的「個人資訊」一詞大致與 GDPR 下的「個人資料」對應。 不過，CCPA 也包含家庭和家用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

本指南中的每一節概述資料控制者組織可以採取的技術程序，以回應對 Microsoft 雲端中個人資料的 DSR 要求

### <a name="gdpr-terminology"></a>GDPR 詞彙

以下提供與本指南相關的詞彙定義：

- **控制者：** 自然人或法人、公家機關、公司或其他主體，不論單獨或與其他單位聯合，會判斷處理個人資料的用途以及方式，其中此類處理的用途以及方式的判斷是根據聯盟與成員國法律，控制者人選或提名控制者的特定準則可由聯盟與成員國法律提供。
- **個人資料和資料主體：** 表示與已識別或可識別之自然人 (以下稱為「資料主體」) 相關的任何資訊；可識別的自然人是可以直接或間接識別的人員，尤其是藉由參照如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身分等一個或多個識別碼來識別。
- **處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。
- **客戶資料：** 由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。 客戶資料包括 (1) 使用者的識別資訊 (例如 Azure Active Directory 中的使用者名稱和連絡人資訊)，以及客戶上傳到特定服務或在特定服務中建立的客戶內容 (例如，Azure 儲存體帳戶中的客戶內容、Azure SQL Database 的客戶內容，或客戶在 Azure 虛擬機器中的虛擬機器映像)。
- **系統產生的記錄：** Microsoft 產生的記錄及相關資料，可協助 Microsoft 向使用者提供企業服務。 系統產生的記錄主要包含經過假名化處理的資料 (例如唯一識別碼)，一般是由系統所產生的數字，無法單獨用來識別個人，但可用來向使用者提供企業服務。 系統產生的記錄也可能包含使用者的身分識別資訊 (例如使用者名稱)。

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>本指南如何協助您符合您的控制者責任

本指南分為兩個部分，說明如何使用 Dynamics 365 產品、服務及系統管理工具，協助您找出Microsoft 雲端中的資料並對其採取動作，以回應根據 GDPR 行使其權利的資料主體的要求。 第一部分介紹客戶資料中包含的個人資料，第二部分介紹在系統產生記錄中擷取的其他假名化個人資料。

- **第 1 部分：針對對客戶資料中包含的個人資料，回應資料主體權利 (DSR) 要求：** 本指南中的第 1 部分將討論如何存取、修正、限制、刪除個人資料，並將其從 Dynamics 365 應用程式 (軟體即服務) 中匯出；系統會將其當作您提供給線上服務的客戶資料中的一部分來處理。
- **第 2 部分：回應假名化資料的資料主體權利要求：** 當您使用 Dynamics 365 企業服務時，Microsoft 會產生一些資訊 (亦即本文件內的*系統產生的記錄*) 以提供服務，此資訊僅限於使用者留下而可識別他們在系統中動作的使用記錄。 在未使用其他資訊的情況下，雖然無法將這項資料歸屬於特定資料主體，但其中有部分在 GDPR 的規範下，仍可能會視為屬於個人資料。 本指南第 2 部分會討論如何存取、刪除及匯入由 Dynamics 365 所產生之系統產生的記錄。

### <a name="preparing-for-data-subject-rights-investigations"></a>準備資料主體權限調查

當資料主體行使其權利並提出要求時，請考慮下列重點：

- 使用資料主體在要求過程中所提供的資訊，適當地識別人員與角色 (例如員工、客戶、供應商)。 這項資訊可能是名稱、員工識別碼或客戶編號或其他識別碼。
- Record the data and time of the request. (You have 30 days to complete the request.)
- Affirm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- 請確認您擁有與要求相關的資訊。

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>第 1 部分：回應客戶資料中所包含個人資料的資料主體權限要求

In the articles below, you'll find information to help you prepare for and respond to DSR requests for personal data included in customer data processed in Dynamics 365. It is important to note that personal data could be present in other categories of data processed by Microsoft during the course of the service of an online services subscription, such as administrator data or support data defined in the Microsoft Privacy Statement. This document is limited to assist you in the process of discovery and management of DSR requests affecting personal data present in the customer data that you have provided to Dynamics 365.

Dynamics 365 is an online service that offers multiple data processing capabilities as a software-as-a-service (SaaS). As such, Dynamics 365 offers a broad array of functionality intended to process a diverse collection of data, which could vary by nature, purpose or other specific attributes, such as sales data, transactions, financials, HR information, etc. In light of this diversity, Dynamics 365 offers multiple forms, fields, schemas, end points, and logic to process customer data, which is also reflected in the multiple ways in which DSR requests could be addressed in each application. When Dynamics 365 applications offer several ways to address specific DSR requests, we will note those in this guide by pointing to the technical descriptions offered by each application.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>尋找客戶資料

回應資料主體權限要求的第一個步驟是搜尋並找出該要求主體的客戶資料。

Classifying customer data appropriately is the cornerstone of working with personal data in Dynamics 365 Customer Engagement business applications. Dynamics 365 for Customer Engagement offers flexibility to build out an application extension around data classification. Proper classification enables you to identify information as personal data, thereby making it possible to locate and retrieve it when responding to requests from a data subject. It can also help enable compliance with legislative and regulatory requirements for collecting and managing personal data.

Microsoft provides capabilities that assist you in responding to data subject rights requests, and thereby accessing customer data. However, it is your responsibility to ensure that personal data is located and classified appropriately.

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

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

***Dynamics 365 Customer Service Insights*** 可讓您使用資料匯出來[提供客戶資料的副本](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)。

***Dynamics 365 for Finance and Operations*** 中的客戶資料可使用完整的實體匯出功能來匯出。 使用[*資料管理與整合實體*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)，租用戶系統管理員可以利用提供的實體、建立新實體或延伸現有、可重複的個人資料的實體，使用[*資料匯入及匯出工作*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)匯出至 Excel 或許多其他常見格式。  另一方面，許多清單可以匯出為靜態 Excel 檔案，以利資料可攜性要求。 將客戶資料匯出至 Excel 後，之後您可以編輯要包含在可攜性要求中的個人資料，然後將檔案儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 您也可以考慮使用「人員搜尋報告」來提供您已分類為個人資料之資料的資料主題。

在 ***Dynamics 365 Business Central*** 中，您可以使用兩種功能將客戶資料的副本提供給資料主體：

您可以將客戶資料匯出為 Excel 檔案。 之後您可以在 Excel 中編輯要包含在可攜性要求中的客戶資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 如需詳細資訊，請參閱[將您的商務資料匯出至 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。

在 ***Dynamics 365 for Talent*** 中，您可以使用[擴充人員搜尋報表](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)，來蒐集資訊以支援對資料主體之個人資料副本的要求。

### <a name="rectifying-customer-data"></a>修正客戶資料

***Dynamics 365 for Customer Engagement*** 提供您以下方法來修正不精準或不完整的客戶資料，或清除客戶資料：

- 使用「尋找客戶資料」中所述的功能來搜尋客戶資料，並在 [客戶參與表單] 中直接編輯資料。 您可在單一資料列層級進行編輯，或直接修改多個資料列。
- 大量編輯多個 Customer Engagement 記錄：您可以利用 Microsoft Office 增益集將資料匯出至 Microsoft Excel、進行變更，然後將已修改的資料從 Excel 匯入至 Dynamics 365 for Customer Engagement。

此外，針對 Dynamics 365 for Marketing，您還可以：

- 藉由直接編輯單一或多個資料列，更新我的資料登陸頁面
- Prepare a [subscription centers](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) page that has as many editable contact fields that can be included. This enables an end user to update their own information as much as possible.

***Dynamics 365 Customer Service Insights*** 也提供讓組織[改正或變更客戶資料](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary)的功能。

在 ***Dynamics 365 for Finance and Operations*** 中，您也可以使用[*自訂工具*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)，但須由您負責決策及實作。

***Dynamics 365 Business Central*** 提供兩個方法來修正不精準或不完整的客戶資料。

To quickly bulk-edit multiple Business Central records, you can export lists to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to correct multiple records, and then publish the modified data from Excel in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

您可以手動編輯內含目標個人資料的資料元素，來變更在任何欄位中所儲存的客戶資料 (例如客戶卡片中客戶的相關資訊)。 如需詳細資訊，請參閱[輸入資料](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)。

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>修改商務交易中項目的簡短備註

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 for Finance and Operations and Dynamics 365 Business Central restrict modifying data in such records.

If you store personal data in business transaction records, the only way to correct, delete, or restrict processing of personal data to honor a data subject's request is to use the Dynamics 365 Business Central [customization capabilities](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index). Th[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)e decision to honor a modification data subject request and implementation thereof is your responsibility.

### <a name="restricting-the-processing-of-customer-data"></a>限制處理客戶資料

當您從資料主體收到限制對客戶資料處理的要求時，可輕易從線上服務擷取受影響的客戶資料，並將其儲存在個別容器 (即，內部部署儲存空間或具有資料隔離功能的個別 Web 服務) 中，與任何雲端應用程式所提供的處理功能隔離。

替代機制，例如資料處理封鎖是由 ***Dynamics 365 商務中心*** 所提供，在其中，使用者能夠封鎖特定資料主體的記錄。 如需詳細資訊，請參閱[限制資料主體的資料處理](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject)。 當記錄標示為已封鎖時，Dynamics 365 Business Central 將不再繼續處理該資料主體的客戶資料。 您無法建立使用封鎖的記錄的新交易。比方說，當客戶或銷售人員遭封鎖時，您無法為客戶建立新發票。

### <a name="deleting-customer-data"></a>刪除客戶資料

當資料主體要求您刪除其客戶資料時，有數個方式可以執行這項操作：

- 大量編輯多個 Dynamics 365 記錄，您可以利用 Microsoft Office 增益集將資料匯出至 Microsoft Excel、進行變更，然後將已修改資料從 Excel 匯入至線上服務。
- 您可以找出您想要刪除的資料，來刪除在任何欄位中儲存的客戶資料，然後手動刪除內含目標客戶資料的資料元素 (就像對代表資料主題的連絡人記錄與包含個人資料的其它記錄使用實刪除)

此外，針對 Dynamics 365 Marketing，刪除連絡人將確保也會移除具有個人資訊的互動資料。 若為任何自訂欄位或實體，您必須自訂您的系統，以確定會從相關記錄中刪除所有客戶資料和/或從連絡人記錄中取消連結，以便移除所有個人資訊。 詳細資訊：[開發人員指南 (行銷)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide)。

***Dynamics 365 Customer Service Insights*** 也提供讓組織[刪除客戶資料](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete)的功能。

或者，您也可以在 ***Dynamics 365 for Finance and Operations*** 中使用[*自訂工具*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)來清除/修改客戶資料。

在 ***Dynamics 365 Business Central*** 中，當資料主體要求您刪除剛好包含在您的客戶資料中的個人資料時，有數個方法可以解決此要求：

- To quickly bulk-edit multiple Business Central records, you can export data to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to delete multiple records, and then publish these changes from Excel back in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- 您可以手動刪除包含目標客戶資料的資料元素，來刪除儲存在任何欄位中的客戶資料。 如需詳細資訊，請參閱[輸入資料](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)。
- 例如，您可以刪除連絡人，然後執行「刪除已取消的互動記錄項目」批次作業來直接刪除客戶資料，以刪除與該連絡人的互動。
- 您可以[刪除包含客戶資料的文件](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents)，例如備忘錄和已過帳的銷售和採購發票。

Besides bulk or individual deletion of discrete records, please note that only terminated workers can be fully deleted from ***Dynamics 365 for Talent***. [Follow these steps to delete terminated workers](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>匯出客戶資料

為了回應資料可攜性要求，***Dynamics 365 for Customer Engagement*** 中的客戶資料可使用完整的實體匯出功能來匯出。 客戶資料可以匯出為靜態 Excel 檔案，以利資料可攜性要求。 之後您可以使用 Excel 來編輯要包含在可攜性要求中的個人資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

針對 ***Dynamics 365 Customer Service Insights***，您可以透過 Azure 管理入口網站[匯出客戶資料](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)。

***Dynamics 365 for Finance and Operations*** 提供[資料管理與整合實體](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)，它使得提供的實體、新建立的實體，或延伸可重複的個人資料的實體，能夠使用[資料匯入和匯出作業](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)匯出至 Excel 或許多其他常見格式。  另一方面，許多清單可以匯出為靜態 Excel 檔案，以利資料可攜性要求。 以此方式將客戶資料匯出至 Excel 後，之後您可以編輯要包含在可攜性要求中的個人資料，然後將檔案儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。

Dynamics 365 for Finance and Operations 和 ***Dynamics 365 for Talent*** 兩者都提供了 [人員搜尋報表]，可將已分類為個人資料的資料提供給資料主體。 

***Dynamics 365 Business Central*** 提供下列功能：

- 您可以將客戶資料匯出為 Excel 檔案。 之後您可以在 Excel 中編輯要包含在可攜性要求中的客戶資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 如需詳細資訊，請參閱[將您的商務資料匯出至 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。
- 您可以將客戶資料匯出為 Excel 檔案。 之後您可以在 Excel 中編輯要包含在可攜性要求中的客戶資料，然後儲存為經常使用的機器可讀取格式，例如 .csv 或 .xml。 如需詳細資訊，請參閱[將您的商務資料匯出至 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>第 2 部分：回應系統所產生記錄的 DSR

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- 產品和服務使用情況資料 (例如使用者活動記錄)
- 使用者搜尋要求和查詢資料
- 作為系統功能與使用者或其他系統互動的產品和服務所產生的資料

Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### <a name="accessing-and-exporting-system-generated-logs"></a>存取和匯出系統所產生的記錄

Admins can access system-generated logs associated with a particular user's use of Dynamics 365 services and applications. To access and export system-generated logs:

1. 請移至 [Microsoft 服務信任入口網站](https://servicetrust.microsoft.com/)，並使用 Dynamics 365 全域系統管理員認證登入。
2. 在頁面頂端的 [隱私權]**** 下拉式清單中，按一下 [資料主體要求]****。
3. 在 [資料主體要求]**** 頁面的 [系統產生的記錄]**** 底下，按一下 [資料記錄匯出]****。
    > [!NOTE]
    > The **Data Log Export** is displayed. Note that a list of export data requests submitted by your organization is displayed.
4. 若要為某個使用者新建要求，請按一下 [建立匯出資料要求]****。

After you create a new request, it will be listed on the **Data Log Export** page where you can track its status. After a request is complete, you can click a link to access the system-generated logs, which will be exported to your organization's Azure storage location within 30 days of creating the request. The data will be saved in common, machine-readable file formats such as JSON or XML. If you don't have an Azure account and Azure storage location, you'll need to create an Azure account and/or Azure storage location for your organization so that the Data Log Export tool can export the system-generated logs.

Azure 可支援這點；我們讓貴組織能以原生 JSON 格式，將資料匯出到您指定的Azure 儲存體容器。[Microsoft Azure 儲存體 - Blob 儲存體簡介](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage)一文。 所擷取的資料不會包含可能造成服務安全性和穩定性受損的資料。

> [!IMPORTANT]
> 您必須是租用戶系統管理員，才能從租用戶中匯出使用者資料。

下表摘要列出系統所產生記錄檔的存取和匯出：

| | |
|:----|:---|
| | |
|**Microsoft 資料記錄檔匯出工具需要花費多少時間才能完成要求？**| This can depend on several factors. In most cases it should complete in one or two days, but it can take up to 30 days. |
|**輸出的格式是什麼？**| 輸出會是機器可讀取的結構化檔案，例如 XML、CSV 或 JSON。 |
|**資料記錄檔匯出工具傳回的資料為何？**| 資料記錄匯出工具會傳回 Microsoft 儲存的系統產生的記錄檔。 匯出的資料會跨越不同的 Microsoft 服務，包括 Office 365、Azure 和 Dynamics。 |
|***誰有權存取資料記錄檔匯出工具，以提交對系統所產生記錄檔的存取要求？**| Dynamics 365 全域系統管理員將有權存取「GDPR 記錄檔管理員」公用程式。 |
|**資料傳回給使用者的方式為何？**| 系統會將資料匯出至貴組織的 Azure 儲存體位置；貴組織的系統管理員將決定是否向使用者顯示此資料，或將此資料傳回給使用者。 |
|**資料在系統產生的記錄檔中看起來會是麼樣子？**| 以 JSON 格式記錄的系統所產生記錄檔範例： <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>刪除系統產生的記錄

若要刪除透過存取要求擷取的系統產生記錄，您必須從服務中移除使用者，然後永久刪除其 Azure Active Directory 帳戶。 如需如何永久刪除使用者的相關指示，請參閱「Azure 資料主體要求」主題中的[步驟 5：刪除](gdpr-dsr-azure.md#step-5-delete)一節。 請注意，一旦永久刪除使用者帳戶就無法復原。 永久刪除使用者帳戶會在 30 天內將使用者資料，從幾乎所有 Dynamics 365 服務產生的系統記錄中移除 (可能危及服務安全性或穩定性的資料除外)。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
