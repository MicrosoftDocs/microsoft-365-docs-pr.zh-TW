---
title: 依據 GDPR 和 CCPA 的資料主體要求
description: 了解 GDPR 和 CCPA 下的使用者權利，以及 Office 365 如何協助企業找出並處理資料，以回應 DSR。
keywords: Office 365、DSR、Microsoft 365、Microsoft 365 教育版、Microsoft 365 文件、GDPR、CCPA
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
titleSuffix: Microsoft GDPR
ms.openlocfilehash: e77fe9c8340608afae3a308ee399809144f6308f
ms.sourcegitcommit: 4cfb8a9c3675d0aefcabd690273e2af85f2e38b0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44211459"
---
# <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的資料主體要求

## <a name="introduction-to-dsrs"></a>DSR 簡介

歐盟[一般資料保護規範 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 賦予人員 (在規範中稱為 *「資料主體」*) 權限，以管理由雇主或其他類型的公司或組織 (稱為 *「資料控制者」* 或簡稱 *「控制者」*) 收集而來的個人資料。個人資料在 GDPR 中的定義廣泛，係指與已識別或可識別的自然人相關的任何資料。GDPR 賦予資料主體對其個人資料的特定權限，這些權限包括取得個人資料複本、要求更正資料、限制資料的處理、刪除資料或以電子格式接收資料，以便轉交給其他控制者。由資料主體向控制者提出對其個人資料採取某項動作的正式要求，稱為 *「資料主體要求」* 或 DSR。控制者有義務盡快考慮每項 DSR，並採取要求的動作來提供實質回應；或針對控制者無法滿足 DSR 的原因進行說明。控制者應向其法律或法務遵循顧問諮詢有關適當處置任何特定 DSR 的方法。

同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。 CCPA 也提供特定揭露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。 銷售的廣泛定義，包括出於有價值的考量而共用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

本指南會討論如何使用 Office 365 產品、服務及系統管理工具，協助您找出並處理個人資料或個人資訊以回應 DSR。 具體而言，這包括如何尋找、存取和處理位於 Microsoft 雲端的個人資料或個人資訊。 以下是本指南中所述程序的快速概觀：

- **探索**：使用搜尋和探索工具，更輕鬆地尋找可能成為 DSR 主體的客戶資料。 收集到可能的回應文件之後，您就可以執行下列步驟中所述的一或多個 DSR 動作來回應要求。 或者，您可能判定該要求不符合組織回應 DSR 的方針。
- **存取：** 擷取在 Microsoft 雲端中常駐的個人資料，並在要求時製作可供資料主體使用的副本。
- **修正：** 在適用情況下，對個人資料進行變更或實行其他要求的動作。
- **限制**：藉由盡可能移除各種 Azure 服務的授權或關閉所需的服務，以限制個人資料的處理。 您也可以從 Microsoft 雲端移除資料，並將它保留在內部部署或另一個位置。
- **刪除：** 永久移除 Microsoft 雲端中常駐的個人資料。
- **匯出/接收 (可攜性)：** 將個人資料或個人資訊以電子複本 (以電腦可讀取的格式) 提供給資料主體。 CCPA 中的個人資訊是任何與已識別或可識別個人相關的資訊。 個人的私人、公開或工作角色之間沒有區別。 定義的「個人資訊」一詞大致與 GDPR 下的「個人資料」對應。 不過，CCPA 也包含家庭和家用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

### <a name="terminology"></a>術語

以下是來自 GDPR 與本指南相關之詞彙的定義。

- **控制者：** 自然人或法人、公家機關、公司或其他主體，不論單獨或與其他單位聯合，會判斷處理個人資料的用途以及方式，其中此類處理的用途以及方式的判斷是根據聯盟與成員國法律，控制者人選或提名控制者的特定準則可由聯盟與成員國法律提供。
- **個人資料和資料主體：** 表示與已識別或可識別之自然人 (以下稱為「資料主體」) 相關的任何資訊；可識別的自然人是可以直接或間接識別的人員，尤其是藉由參照如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身分等一個或多個識別碼來識別。
- **處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。
- **客戶資料：** 由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。 客戶資料包括 (1) 使用者的識別資訊 (例如 Azure Active Directory 中的使用者名稱和連絡人資訊)，以及客戶上傳到或在特定服務中建立的客戶內容 (例如，Word 或 Excel 文件中的客戶內容，或是在 Exchange Online 電子郵件中的文字；新增至 SharePoint Online 網站或儲存至商務用 OneDrive 帳戶的客戶內容)。
- **系統產生的記錄：** Microsoft 產生的記錄及相關資料，可協助 Microsoft 向使用者提供企業服務。 系統產生的記錄主要包含經過假名化處理的資料 (例如唯一識別碼)，一般是由系統所產生的數字，無法單獨用來識別個人，但可用來向使用者提供企業服務。 系統產生的記錄也可能包含使用者的身分識別資訊 (例如使用者名稱)。

### <a name="how-to-use-this-guide"></a>如何使用本指南

為了協助您找出與使用案例相關的資訊，本指南分成四個部分。

- **[第 1 部分：回應 DSR 的客戶資料](#part-1-responding-to-dsrs-for-customer-data)：** *客戶資料*是指貴公司日常營運作業所產生並儲存在 Office 365 內的資料。 最常用 Office 365 應用程式的範例，可讓您撰寫包含 Word、Excel、PowerPoint、Outlook 和 OneNote 的資料。 Office 365 也包含這些應用程式 (例如 SharePoint Online、Teams 和表單)，幫助您更有效與他人共同作業。 本指南第 1 部分將討論如何存取、修正、限制、刪除及匯出 Office 365 應用程式 (已在 Office 365 線上服務中用來編寫和儲存資料) 的資料。 這宣告 Microsoft 做為貴公司產品和服務的資料處理者，因此可提供您的租用戶系統管理員使用 DSR 功能。
- **[第 2 部分：按照 Office 365 產生的見解來回應 DSR ](#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)：** Office 365 透過如 Delve、MyAnalytics 及「工作場所分析」這類服務提供特定見解。 本指南第 2 部分會說明這些見解是如何產生的，以及如何回應與其相關的 DSR。
- **[第 3 部分：回應系統所產生記錄的 DSR](#part-3-responding-to-dsrs-for-system-generated-logs)：** 當您使用 Office 365 企業服務時，Microsoft 會產生部分資訊，例如服務記錄，其中記錄線上服務中功能的使用或效能。 大部分服務產生的資料都包含由 Microsoft 所產生且經過假名化處理的識別碼，因此這個類別通常會在本文件內稱為 *「系統所產生的記錄」*。 在未使用其他資訊的情況下，雖然無法將這項資料歸屬於特定資料主體，但其中有部分在 GDPR 的「個人資料」定義下，仍可能會視為屬於個人資料。 本指南第 3 部分會討論如何存取、刪除及匯出系統所產生的記錄。
- **[第 4 部分：其他協助您處理 DSR 的資源](#part-4-additional-resources-to-assist-you-with-dsrs) - **本指南第 4 部分會列出使用特定的 Office 365 產品和服務時，Microsoft 是資料控制者的有限案例。

>[!NOTE]
>在大多數情況下，當貴組織中的使用者使用 Microsoft Office 365 產品和服務時，您是資料控制者，而 Microsoft 是處理者。身為資料控制者，您有責任直接回應資料主體。為了協助您處理此情形，本指南第 1 至 3 部分詳述可供貴組織回應 DSR 要求的技術功能。不過，在少數有限的案例下，當人員使用特定的 Office 365 產品和服務時，Microsoft 將是資料控制者。在這些情況下，第 4 部分中的資訊提供資料主體如何將 DSR 要求提交給 Microsoft 的指導方針。

### <a name="office-365-national-clouds"></a>Office 365 國家雲

Microsoft Office 365 服務也可在下列國家雲環境中取得：[Office 365 Germany](https://docs.microsoft.com/microsoft-365/admin/admin-overview/learn-about-office-365-germany)、[由 21Vianet (中國) 運作的 Office 365](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china) 和 [Office 365 US Government](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans)。本文件中描述的大多數用於管理資料主體要求的指引會套用到這些國家雲環境。不過，由於這些環境的隔離性質，所以有一些例外狀況。在特定子節中值得注意的是，這些例外狀況會在對應的附註中引出。

### <a name="hybrid-deployments"></a>混合式部署

您的組織包含的 Microsoft 供應項目可能結合雲端式服務與內部部署伺服器產品。一般而言，混合式部署通常會共用使用者帳戶 (身分識別管理) 和存在於雲端及內部部署環境中的資源 (例如信箱、網站和資料)。常見的混合式案例包括：

- Exchange 混合式部署，其中部分使用者擁有內部部署信箱，而其他使用者擁有 Exchange Online 信箱。
- SharePoint 混合式部署，其中的網站和檔案伺服器是在內部部署環境中，而商務用 OneDrive 帳戶則是在 Office 365 中。
- 與 Azure Active Directory 同步處理的內部部署身分識別管理系統 (Active Directory)，也就是 Office 365 中的基礎目錄服務。

回應 DSR 要求時，您可能必須判斷回應 DSR 要求的資料是在 Microsoft 雲端或在內部部署組織中，然後採取適當的步驟來回應該要求。Office 365 資料主體要求指南 (本指南) 會提供回應雲端資料的指導方針。如需您內部部署組織中資料的指導方針，請參閱[適用於 Office 內部部署伺服器的 GDPR](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers)。

## <a name="part-1-responding-to-dsrs-for-customer-data"></a>第 1 部分：回應客戶資料的 DSR

回應客戶資料 DSR 的指導方針分成下列四節：

- [使用內容搜尋電子文件探索工具來回應 DSR](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)
- [使用應用程式內功能來回應 DSR](#using-in-app-functionality-to-respond-to-dsrs)
- [回應 DSR 修正要求](#responding-to-dsr-rectification-requests)
- [回應 DSR 限制要求](#responding-to-dsr-restriction-requests)

### <a name="how-to-determine-the-office-365-applications-that-may-be-in-scope-for-a-dsr-for-customer-data"></a>如何判斷可能在客戶資料中 DSR 範圍內的 Office 365 應用程式

為了協助您決定要搜尋個人資料的位置或要搜尋的內容，識別貴組織中的人員可以用來建立資料，並將其儲存在 Office 365 的 Office 365 應用程式，很有幫助。 知道此資訊可縮小 DSR 範圍內的 Office 365 應用程式，並可協助您決定如何搜尋並存取與 DSR 相關的個人資料。 具體來說，這表示您是否可以使用「內容搜尋」工具，或是否必須使用建立資料所在應用程式中的應用程式內功能。

有種方式可快速識別出貴組織中的人員用來建立客戶資料的 Office 365 應用程式，就是判斷貴組織的商務用 Microsoft 365 訂閱中包含哪些應用程式。若要這麼做，您可以存取 Office 365 管理入口網站中的使用者帳戶，並查看產品授權資訊。請參閱[將授權指派給使用者](../admin/manage/assign-licenses-to-users.md)。

## <a name="using-the-content-search-ediscovery-tool-to-respond-to-dsrs"></a>使用內容搜尋電子文件探索工具來回應 DSR

在大型資料集內尋找貴組織使用 Office 365 建立並儲存的個人資料時，建議您先考量人員最有可能使用哪些應用程式來撰寫您正在尋找的資料。Microsoft 估計超過 90% 儲存在 Office 365 中的組織資料，是以 Word、Excel、PowerPoint、OneNote 及 Outlook 撰寫的。以這些 Office 應用程式 (即使是透過企業用 Microsoft 365 應用程式或 Office 永久授權購買) 所撰寫的文件，最有可能儲存在 SharePoint Online 網站上、使用者的商務用 OneDrive 帳戶中，或使用者的 Exchange Online 信箱中。這表示您可以使用內容搜尋電子文件探索工具，跨 SharePoint Online 網站、商務用 OneDrive 帳戶，以及 Exchange Online 信箱 (包括與 Microsoft 365 群組、Microsoft Teams、EDU 作業相關聯的網站及信箱) 進行搜尋 (以及執行其他 DSR 相關動作)，來尋找可能與調查中 DSR 相關的文件和信箱項目。您也可以使用內容搜尋工具來探索以其他 Office 365 應用程式撰寫的客戶資料。

下表列出人員用來建立客戶撰寫內容，而且可以使用內容搜尋來探索的 Office 365 應用程式。 DSR 指南的此節可提供探索、存取、匯出及刪除資料 (使用這些 Office 365 應用程式所建立) 的指導方針。

***表 1：可以使用內容搜尋來尋找客戶資料的應用程式***

| | |
| :---: | :---:|
![行事曆圖示](../media/O365-DSR-Doc-Final_image3.png) <br> 行事曆 | ![SharePoint 圖示](../media/o365-sharepoint-64x64.png) <br> SharePoint  |
| ![Excel 圖示](../media/o365-excel-64x64.png) <br> Excel | ![商務用 Skype 圖示](../media/o365-skypeforbusiness-64x64.png) <br> 商務用 Skype |
| ![Office Lens 圖示](../media/o365-lens-64x64.png) <br> Office Lens | ![工作圖示](../media/O365-DSR-Doc-Final_image8.png) <br> 工作 |
| ![OneDrive 圖示](../media/o365-OneDrive-64x64.png) <br> 商務用 OneDrive |![Teams 圖示](../media/o365-teams-64x64.png) <br> Teams |
| ![OneNote 圖示](../media/o365-onenote-64x64.png) <br> OneNote| ![待辦事項圖示](../media/o365-todo-64x64.png) <br> To Do |
| ![Outlook 圖示](../media/o365-outlook-64x64.png) <br> Outlook/Exchange | ![影片圖示](../media/O365-DSR-Doc-Final_image14.png) <br> 影片 |
| ![多人圖示](../media/O365-DSR-Doc-Final_image15.png) <br> 多人 | ![Visio 圖示](../media/o365-visio-64x64.png) <br> Visio |
| ![PowerPoint 圖示](../media/o365-powerpoint-64x64.png) <br> PowerPoint | ![Word 圖示](../media/o365-word-64x64.png) <br> Word
||

>[!NOTE]
>內容搜尋電子文件探索工具並未在[由 21Vianet 運作 (中國) 的 Office 365](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china) 中提供。這表示您無法使用這項工具來搜尋和匯出表格 1 中所顯示 Office 365 應用程式中的客戶資料。不過，您可以在 Exchange Online 中使用「就地電子文件探索」工具來搜尋使用者信箱中的內容。您也可以在 SharePoint Online 中使用「電子文件探索中心」來搜尋 SharePoint 網站和 OneDrive 帳戶中的內容。或者，您可以要求文件擁有者協助您尋找並進行內容變更或刪除，或視需要匯出內容。如需詳細資訊，請參閱：</br><br> * [建立就地電子文件探索搜尋](https://docs.microsoft.com/exchange/create-in-place-ediscovery-search-exchange-2013-help)<br> * [在 SharePoint Online 中設定電子文件探索中心](https://support.office.com/article/Set-up-an-eDiscovery-Center-in-SharePoint-Online-A18F8975-AA7F-43B4-A7D6-001D14744D8E)

### <a name="using-content-search-to-find-personal-data"></a>使用內容搜尋來尋找個人資料

回應 DSR 的第一個步驟是先找出個人資料，也就是 DSR 的主體。 這包括 (在 Office 365 中所有貴組織的資料之間) 使用 Office 365 電子文件探索工具來搜尋個人資料，或直接移至建立資料的原生應用程式。 第一個步驟 (尋找並檢閱上述的個人資料)，可協助您判斷 DSR 是否符合貴組織的需求，以便接受或拒絕。 例如，在找出並檢閱個人資料後，您可能因為這樣做會對其他人的權利和自由造成負面影響，或是因為個人資料包含在貴組織保有合法商業利益的公司記錄中，而判斷要求不符合貴組織的需求。

如先前所述，Microsoft 估計有超過 90% 的組織資料是使用 Office 應用程式 (例如 Word 和 Excel) 建立的。這表示，您可以使用安全性與合規性中心內的內容搜尋，來搜尋大部分與 DSR 相關的資料。

本指南假設，針對可回應 DSR 要求的個人資料，您或搜尋人員熟悉安全性與合規性中心內的「內容搜尋」工具，或有使用此工具的經驗。如需使用內容搜尋的一般指導方針，請參閱 [Office 365 中的內容搜尋](https://docs.microsoft.com/microsoft-365/compliance/content-search)。請確定您已將安全性與合規性中心內的必要權限，指派給執行搜尋的人員。應將此人員新增為安全性與合規性中心內「電子文件探索管理員」角色群組的成員；請參閱[指派安全性與合規性中心內的電子文件探索權限](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)。請考慮將貴組織中涉及調查 DSR 的人員也新增至「電子文件探索管理員」角色群組，以便他們在內容搜尋工具中執行必要動作，例如預覽和匯出搜尋結果。不過，除非您設定合規性界限 (如[這裡](#set-up-compliance-boundaries-to-limit-the-scope-of-content-searches)所述)，否則請注意電子文件探索管理員可以搜尋貴組織中的所有內容位置，包括可能與 DSR 調查不相關的內容位置。

找到資料後，接著您可以執行指定的動作來滿足資料主體的要求。

>[!NOTE]
>在 Office 365 Germany 中，安全性與合規性中心位於 https://protection.office.de。

#### <a name="searching-content-locations"></a>搜尋內容位置

您可以使用「內容搜尋」工具來搜尋下列類型的內容位置。

- Exchange Online 信箱。 這包括與 Microsoft 365 群組和 Microsoft Teams 相關聯的信箱
- Exchange Online 公用資料夾
- SharePoint Online 網站。 這包括與 Microsoft 365 群組和 Microsoft Teams 相關聯的網站
- 商務用 OneDrive 帳戶

>[!NOTE]
>本指南假設，可能與 DSR 調查相關的所有資料都會儲存在 Office 365 中 (也就是說，儲存在 Microsoft 雲端中)。儲存在使用者的本機電腦上，或貴組織檔案伺服器上內部部署的資料，不在 Office 365 中所儲存資料的 DSR 調查範圍內。如需有關針對內部部署組織中的資料回應 DSR 要求的指導方針，請參閱[適用於內部部署 Office 伺服器的 GDPR](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers)。

#### <a name="tips-for-searching-content-locations"></a>搜尋內容位置的秘訣

- 一開始先搜尋貴組織中的所有內容位置 (您可以在單一搜尋中進行搜尋)，來快速判斷哪些內容位置包含符合搜尋查詢的項目。 然後，您可以重新執行搜尋，並將搜尋範圍縮小至包含相關項目的特定位置。
- 請使用搜尋統計資料，來識別包含符合搜尋查詢項目的熱門位置。請參閱[檢視內容搜尋結果的關鍵字統計資料](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search)。
- 搜尋稽核記錄，以找出身為 DSR 主體的使用者最近執行過的檔案及資料夾活動。 搜尋稽核記錄將會傳回稽核記錄的清單，其中會包含使用者最近與其互動之資源的名稱和位置。 您可以使用這些資訊來組建內容搜尋查詢。 請參閱[在安全性與合規性中心搜尋稽核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

#### <a name="building-search-queries-to-find-personal-data"></a>組建搜尋查詢來尋找個人資料

您正在調查的 DSR 很可能會包含可在關鍵字搜尋查詢中用來搜尋個人資料的識別碼。 以下是一些可用於搜尋查詢中以尋找個人資料的常用識別碼：

- 電子郵件地址或別名
- 電話號碼
- 郵寄地址
- 員工識別碼
- 國家身分證號碼或歐盟成員版本的社會安全號碼

您正在調查的 DSR 很可能會有可用於搜尋查詢的識別碼和其他詳細資料 (關於要求主體的個人資料)。

只搜尋一個電子郵件地址或員工 ID 可能會傳回多個結果。 若要縮小搜尋範圍，以便只傳回與 DSR 最相關的內容，您可以對搜尋查詢新增條件。 當您新增條件時，**AND** 布林值運算子會以邏輯方式連接關鍵字和搜尋條件。 這表示搜尋結果只會傳回*同時符合*關鍵字和條件的項目。

下表列出一些可用來縮小搜尋範圍的條件。這個表格也會列出一些值，可用於每個條件中來搜尋特定的文件類型和信箱項目。

***表 2：使用條件縮小搜尋範圍***

||||
| :--- | :--- |:--- |
|**條件**|**描述** |**條件值的範例**|
| 檔案類型 | 文件或檔案的副檔名。 請使用此條件以搜尋 Office 365 應用程式建立的 Office 文件及檔案。 當搜尋位於 SharePoint Online 網站和商務用 OneDrive 帳戶中的資料時，請使用此條件。<br/>對應的文件屬性為 filetype。 <br/>如需您可以搜尋之副檔名的完整清單，請參閱 SharePoint 中預設已編目的副檔名及已剖析的檔案類型](https://technet.microsoft.com/library/jj219530.aspx)。|&nbsp;&bull;&nbsp;&nbsp;csv – 搜尋逗號分隔值 (CSV) 檔案。Excel 檔案可以儲存為 CSV 格式，而且 CSV 檔案可以輕鬆地匯入 Excel 中 <br><br>&bull;&nbsp;&nbsp;docx – 搜尋 Word 檔案 <br><br>&bull;&nbsp;&nbsp;mpp - 搜尋 Project 檔案<br/><br>&bull;&nbsp;&nbsp;one - 搜尋 OneNote 檔案 <br><br>&bull;&nbsp;&nbsp;pdf – 搜尋儲存為 PDF 格式的檔案 <br><br>&bull;&nbsp;&nbsp;pptx – 搜尋 PowerPoint 檔案 <br><br>&bull;&nbsp;&nbsp;xlxs – 搜尋 Excel 檔案 <br><br>&bull;&nbsp;&nbsp;vsd – 搜尋 Visio 檔案 <br><br>&bull;&nbsp;&nbsp;wmv – 搜尋 Windows Media 視訊檔 <br>|
| 訊息類型 | 要搜尋的電子郵件類型。 使用此條件，在信箱中搜尋聯絡人 (人員)、會議 (行事曆) 或商務用 Skype 交談。 對應的電子郵件屬性是 *kind*。|&bull;&nbsp;&nbsp;*contacts – 搜尋信箱中我的連絡人清單 (人員)<br><br>&bull;&nbsp;&nbsp;* email — 搜尋電子郵件 <br><br>&bull;&nbsp;&nbsp;*im — 搜尋商務用 Skype 交談<br><br>&bull;&nbsp;&nbsp;* meetings — 搜尋約會及會議邀請 (行事曆) <br><br>&bull;&nbsp;&nbsp;*tasks – 搜尋我的工作清單 (工作)；使用此值也將傳回以 Microsoft ToDo 建立的工作。<br>|
| 合規性標籤 |指派給電子郵件訊息或文件的標籤。標籤是用來分類電子郵件和文件，以進行資料控管；並根據標籤定義的分類強制執行保留規則。請使用此條件，來搜尋已自動或手動指派標籤的項目。<br/>這是對 DSR 調查很有用的條件，因為組織可能會使用標籤來分類與資料隱私權相關的內容，或含有個人資料或敏感性資訊的內容。請參閱 [Office 365 中的標籤概觀](https://docs.microsoft.com/microsoft-365/compliance/labels)中的＜使用內容搜尋來尋找所有已套用特定標籤的內容＞一節。|compliancetag="personal data"|
||||

有許多其他的電子郵件和文件內容及搜尋條件，可用來建立更複雜的搜尋查詢。如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)說明主題中的下列各節。

- [可搜尋的電子郵件屬性](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [可搜尋的網站 (文件) 屬性](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [搜尋條件](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)

#### <a name="searching-for-personal-data-in-sharepoint-lists-discussions-and-forms"></a>搜尋 SharePoint 清單、討論和表單中的個人資料

除了搜尋文件中的個人資料外，您也可以使用內容搜尋來搜尋使用原生 SharePoint Online 應用程式所建立的其他類型資料。這包括使用 SharePoint 清單、討論及表單所建立的資料。當您執行內容搜尋並搜尋 SharePoint Online 網站 (或商務用 OneDrive 帳戶) 時，在搜尋結果中將傳回清單、討論及表單中符合搜尋準則的資料。

##### <a name="examples-of-search-queries"></a>搜尋查詢的範例

以下是幾個搜尋查詢的範例，會使用關鍵字和條件來搜尋個人資料，以回應 DSR。 這些範例顯示兩種版本的查詢：其中一種是關鍵字語法 (條件包含在 [關鍵字] 方塊中)，另一種則顯示具有條件的 GUI 型查詢。

##### <a name="example-1"></a>範例 1

此範例會傳回位於 SharePoint Online 網站和商務用 OneDrive 帳戶的 Excel 檔案，其中包含指定的電子郵件地址。 如果電子郵件地址出現在檔案中繼資料內，則可能會傳回這些檔案。

***關鍵字語法***

```Query
pilar@contoso.com AND filetype="xlxs"
```

***GUI***

![關鍵字對話方塊](../media/O365-DSR-Doc_image18.png)

##### <a name="example-2"></a>範例 2

此範例會傳回位於 SharePoint Online 網站和商務用 OneDrive 帳戶的 Excel 或 Word 檔案，其中包含指定的員工識別碼或出生日期。

(98765 OR "01-20-1990") AND (filetype="xlxs" OR filetype="docx")

***GUI***

![關鍵字對話方塊](../media/O365-DSR-Doc_image19.png)

##### <a name="example-3"></a>範例 3

此範例會傳回包含所指定識別碼 (即法國社會安全號碼 INSEE) 的電子郵件訊息

```Query
"1600330345678 97" AND kind="email"
```

***GUI***

![關鍵字對話方塊](../media/O365-DSR-Doc_image20.png)

#### <a name="working-with-partially-indexed-items-in-content-search"></a>在內容搜尋中使用已局部編製索引的項目

已部分編製索引的項目 (也稱為「未編製索引的項目」**) 是 SharePoint Online 和商務用 OneDrive 網站上，基於某種原因而未完全編製索引以利搜尋的 Exchange Online 信箱項目和文件，這表示無法使用「內容搜尋」來加以搜尋。 大部分的電子郵件訊息和網站文件都可成功編製索引，因為落在 [Office 365 索引限制](https://docs.microsoft.com/microsoft-365/compliance/limits-for-content-search)內。 電子郵件訊息或檔案未編製索引以利搜尋的原因包括：

- 檔案類型[無法辨識或不支援索引編製功能](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)。 雖然有時候檔案類型會支援索引編製，但在編製特定檔案的索引時發生錯誤。
- 電子郵件訊息所具有的附加檔案 (例如影像檔) 缺乏有效的處理常式，這是已局部編製索引的電子郵件項目最常見的原因
- 電子郵件訊息的附加檔案太大，或有太多個附加檔案

我們建議您深入了解已局部編製索引的項目，讓您可在回應 DSR 要求時使用。如需詳細資訊，請參閱：

- [位於 Office 365 中內容搜尋的已局部編製索引項目](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)
- [調查 Office 365 電子文件探索中已局部編製索引的項目](https://docs.microsoft.com/microsoft-365/compliance/investigating-partially-indexed-items-in-ediscovery)
- [匯出未編製索引的項目](https://docs.microsoft.com/microsoft-365/compliance/export-search-results#unidexeditems)

#### <a name="tips-for-working-with-partially-indexed-items"></a>使用已局部編製索引項目的提示

可回應 DSR 調查的資料可能位於已部分編製索引的項目中。以下是一些使用已部分編製索引項目的建議：

- 執行搜尋後，估計部分項目的數字會顯示在搜尋統計資料中。 此估計值不會包含 SharePoint Online 和商務用 OneDrive 中部分編製索引的項目。 匯出內容搜尋的報告，以取得部分編製索引項目的相關資訊。 **未編製索引的 Items.csv** 報告包含未編製索引項目的相關資訊，包含項目的位置、URL (如果項目位於 SharePoint Online 或商務用 OneDrive)，以及 (郵件) 主旨行或文件的名稱。 如需詳細資訊，請參閱[匯出內容搜尋報告](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report)。

- 隨著內容搜尋一起傳回的已局部編製索引項目統計資料和清單，都是來自所搜尋內容位置中的局部項目。

- 若要擷取可能會回應 DSR 調查的已局部編製索引項目，您可以執行下列其中一個動作。

##### <a name="export-all-partially-indexed-items"></a>匯出所有已局部編製索引的項目

您可以從搜尋內容的位置匯出內容搜尋結果和部分編製索引的項目。 您也可以只匯出部分編製索引項目。 之後，您可以在原生應用程式中開啟並檢視內容。 您必須使用此選項，才能從 SharePoint Online 和商務用 OneDrive 匯出項目。 請參閱[從安全性與合規性中心匯出搜尋結果](https://docs.microsoft.com/microsoft-365/compliance/export-search-results)。

##### <a name="export-a-specific-set-of-partially-indexed-items-from-mailboxes"></a>從信箱中匯出一組特定的已局部編製索引項目

您可以重新執行內容搜尋來搜尋部分編製索引項目的特定清單，然後再將其匯出，而不是從搜尋匯出所有部分編製索引的信箱項目。 您可以只針對信箱項目匯出項目。 請參閱[在 Office 365 中準備目標內容搜尋的 CSV 檔案](https://docs.microsoft.com/microsoft-365/compliance/csv-file-for-an-id-list-content-search)。

### <a name="next-steps"></a>後續步驟

找到與 DSR 相關的個人資料後，請務必保留您用於找到該資料的特定內容搜尋。 您可能會重複使用完成 DSR 回應程序中的其他步驟，例如，[取得內容副本](#providing-a-copy-of-personal-data)、[匯出內容](#exporting-personal-data)或[永久刪除內容](#deleting-personal-data)。

### <a name="additional-considerations-for-selected-applications"></a>所選應用程式的其他考量事項

下列各節說明您在下列 Office 365 應用程式中搜尋資料時應該記住的事項。

- [Office Lens](#office-lens)
- [商務用 OneDrive 和 SharePoint 體驗設定](#onedrive-for-business-and-sharepoint-online-experience-settings)
- [Microsoft Teams 教育版](#microsoft-teams-for-education)
- [Microsoft To-Do](#microsoft-to-do)
- [商務用 Skype](#skype-for-business)

#### <a name="office-lens"></a>Office Lens

使用 Office Lens (執行 iOS、Android 和 Windows 之裝置支援的相機應用程式) 的人員可以拍攝白板、文件的紙本、名片及含有大量文字的其他項目。 Office Lens 使用光學字元辨識技術，其會擷取影像中的文字，並將之儲存至 Word、PowerPoint 和 OneNote 等 Office 文件或 PDF 檔案。 之後，使用者可能將包含影像內文字的檔案，上傳到 Office 365 的商務用 OneDrive 帳戶。 那代表您可以使用內容搜尋工具來搜尋、存取、刪除和匯出檔案中的資料，這些檔案是從 Office Lens 影像建立而來。 如需 Office Lens 的詳細資訊，請參閱：

- [IOS 版 Office Lens](https://support.microsoft.com/zh-TW/office/microsoft-office-lens-for-ios-fbdca5f4-1b1b-4391-a931-dc1c2582397b)
- [Android 版 Office Lens](https://support.office.com/article/Office-Lens-for-Android-ec124207-0049-4201-afaf-b5874a8e6f2b)
- [Windows 版 Office Lens](https://support.microsoft.com/zh-TW/office/office-lens-for-windows-577ec09d-8da2-4029-8bb7-12f8114f472a)

#### <a name="onedrive-for-business-and-sharepoint-online-experience-settings"></a>商務用 OneDrive 和 SharePoint Online 體驗設定

在商務用 OneDrive 帳戶和 SharePoint Online 網站中，除了儲存使用者所建立的檔案外，這些服務也會儲存提供各種體驗的使用者相關資訊。這些資訊大多可讓貴組織中仍在職的使用者，利用產品內功能進行存取。下列資訊可提供使用者存取、檢視及匯出商務用 OneDrive 和 SharePoint Online 應用程式資料的指導方針。

##### <a name="sharepoint-user-profiles"></a>SharePoint 使用者設定檔

使用者的 Delve 設定檔可讓使用者維護 SharePoint Online 使用者設定檔中所儲存的內容，包括生日、行動電話號碼 (及其他連絡人資訊)、本人相關資訊、專案、技能和專業知識、學校和教育程度、興趣，以及嗜好。

###### <a name="end-users"></a>使用者

使用者可以使用 Delve 設定檔體驗來探索、存取及修正 SharePoint Online 使用者設定檔資料。如需詳細資料，請參閱[在 Office Delve 中檢視和更新您的設定檔](https://support.office.com/article/view-and-update-your-profile-in-office-delve-4e84343b-eedf-45a1-aeb9-8627ccca14ba)。

使用者要存取其 SharePoint 設定檔資料的另一種方法，就是移至其商務用 OneDrive 帳戶 URL 下的 **EditProfile.aspx** 路徑，來存取商務用 OneDrive 帳戶中的 [編輯設定檔頁面]****。 例如，對於使用者 <strong>user1@contoso.com</strong>，使用者的商務用 OneDrive 帳戶位於：

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/OneDrive.aspx`
```

編輯設定檔頁面的 URL 為：

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/EditProfile.aspx`
```

來自 Azure Active Directory 的屬性無法在 SharePoint Online 內變更。 不過，使用者可以移至其 [帳戶]**** 頁面，方法是在 Office 365 頁首選取其**相片**，然後選取 [我的帳戶]****。 在此處變更屬性可能要求使用者與其系統管理員合作以發現、存取或修正使用者設定檔屬性。

###### <a name="admins"></a>系統管理員

系統管理員可以在 SharePoint 系統管理中心存取和修正設定檔屬性。 在 [SharePoint 系統管理中心]****，按一下 [使用者設定檔]**** 索引標籤。按一下 [管理使用者設定檔]****、輸入使用者名稱，然後按一下 [尋找]****。 系統管理員可以用滑鼠右鍵按一下任何使用者，然後選取 [編輯我的設定檔]****。 來自 Azure Active Directory 的屬性無法在 SharePoint Online 內變更。

系統管理員可以在 SharePoint Online PowerShell 中使用 **Export-SPOUserProfile** Cmdlet，匯出使用者的所有使用者設定檔屬性。請參閱 [Export-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserprofile?view=sharepoint-ps)。

如需使用者設定檔的詳細資訊，請參閱[在 SharePoint 系統管理中心管理使用者設定檔](https://docs.microsoft.com/sharepoint/manage-user-profiles)。

##### <a name="user-information-list-on-sharepoint-online-sites"></a>SharePoint Online 網站上的使用者資訊清單

已經將部分使用者的 SharePoint 使用者設定檔與每個網站的使用者資訊清單同步處理，而這些網站是使用者造訪或有權存取的網站。 這會由 SharePoint Online 體驗 (例如，文件庫中的「人員」欄) 用於顯示關於使用者的基本資訊，例如文件建立者的名稱。 使用者資訊清單中的資料會與 SharePoint 使用者設定檔中儲存的資訊相符，而且如果來源變更，則會自動修正。 對於已刪除的使用者，這項資料仍會保留與其互動的網站中，以獲得 SharePoint 欄位的參考完整性。 

系統管理員可以控制哪些屬性可在 SharePoint 系統管理中心內複製。若要這麼做：

1. 移至 [SharePoint 系統管理中心]****，並按一下 [使用者設定檔]**** 索引標籤。
2. 按一下 [管理使用者屬性]**** 來查看屬性清單。
3. 以滑鼠右鍵按一下任何屬性，然後選取 [編輯]**** 並調整各種設定。
4. 在 [原則設定]**** 下，可複製的屬性會控制屬性是否將在使用者資訊清單上顯示。 請注意，並非所有屬性都支援調整此項目。

系統管理員可以在 SharePoint Online PowerShell 中使用 **Export-SPOUserInfo** Cmdlet，匯出使用者的所有使用者資訊屬性。請參閱 [Export-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserinfo?view=sharepoint-ps)。

##### <a name="onedrive-for-business-experience-settings"></a>商務用 OneDrive 體驗設定

使用者的商務用 OneDrive 體驗會儲存資訊，以協助使用者尋找並導覽至他們感興趣的內容。這些資訊大多可讓使用者利用產品內功能加以存取。系統管理員可以使用 [PowerShell Script](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) 和 [SharePoint 用戶端物件模型 (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) (英文) 命令來匯出資訊。

如需有關設定、儲存方式及匯出方式的詳細資訊，請參閱[匯出商務用 OneDrive 體驗設定](https://docs.microsoft.com/sharepoint/export-odfb-lists)。

##### <a name="onedrive-for-business-and-sharepoint-online-search"></a>商務用 OneDrive 和 SharePoint Online 搜尋

商務用 OneDrive 和 SharePoint Online 中的應用程式內搜尋體驗，會將使用者的搜尋查詢儲存 30 天，以提高搜尋結果的相關性。系統管理員可以在 SharePoint Online PowerShell 中使用 **Export-SPOQueryLogs** Cmdlet 來匯出使用者的搜尋查詢。請參閱 [Export-SPOQueryLogs](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spoquerylogs?view=sharepoint-ps)。

#### <a name="microsoft-teams-for-education"></a>Microsoft Teams 教育版

Microsoft Teams 教育版提供兩個額外的共同作業功能 (「作業」和「OneNote 課程筆記本」)，老師和學生可以使用這些功能，來建立並儲存個人資料。您可以使用內容搜尋來探索兩者中的資料。

##### <a name="assignments"></a>作業

與「作業」相關聯的學生檔案，會儲存在對應的 Teams SharePoint Online 網站文件庫中。IT 系統管理員可以使用內容搜尋工具，來搜尋與作業相關的學生檔案。例如，系統管理員可以搜尋組織中的所有 SharePoint Online 網站，並在搜尋查詢中使用學生的名稱、課程或作業名稱，來尋找與 DSR 相關的資料。

還有其他與作業相關，但未儲存在課程小組 SharePoint Online 網站中的資料，這表示無法使用內容搜尋來探索。這包括：

- 老師當成作業的一部分而指派給學生的檔案
- 學生的成績和老師的意見反應
- 每個學生針對作業所提交的文件清單
- 作業中繼資料

對於這種類型的資料，IT 系統管理員或資料擁有者 (例如老師) 可能需要登入課程小組中的「作業」，才能尋找與 DSR 相關的資料。

##### <a name="onenote-class-notebook"></a>OneNote 課程筆記本

OneNote 課程筆記本會儲存在課程小組 SharePoint Online 網站中。課程中的每位學生都有與老師共用的私人筆記本。另外，還有老師可與學生共用文件的內容文件庫，以及適用於課程中所有學生的共同作業空間。您可使用「內容搜尋」來探索與這些功能相關的資料。

以下是搜尋「課程筆記本」的特定指導方針。

1. 請使用下列搜尋準則來執行內容搜尋：

   - 搜尋所有 SharePoint Online 網站

   - 包括課程小組的名稱作為搜尋關鍵字，例如 "9C Biology"。

2. 預覽搜尋結果，並尋找對應至「課程筆記本」的項目。
3. 選取該項目，然後複製詳細資料窗格中顯示的資料夾路徑。這是「課程筆記本」的根資料夾。
4. 編輯您在步驟 1 所建立的搜尋，並將關鍵字查詢中的課程名稱取代為「課程筆記本」的資料夾路徑，然後在資料夾路徑前面加上 **path** 網站屬性，例如，**path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/"**。請務必包括引號和後置斜線。
5. 新增搜尋條件、選取「檔案類型」條件，然後針對檔案類型的值使用一個條件。 這會在搜尋結果中傳回所有 OneNote 檔案。 產生的關鍵字語法可能類似下列內容：[](#building-search-queries-to-find-personal-data)

    ```Query
   path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/" AND filetype="one"
   ```

6.  請重新執行內容搜尋。 搜尋結果應該會包含來自課程小組的「課程筆記本」中所有的 OneNote 檔案。

#### <a name="microsoft-to-do"></a>Microsoft To-Do

Microsoft To-Do 中的工作 (稱為*待辦事項*，儲存在*待辦事項清單*)，會在使用者的 Exchange Online 信箱中儲存為工作。 這表示您可以使用內容搜尋工具來搜尋、存取、刪除及匯出待辦事項。 如需詳細資訊，請參閱[設定 Microsoft To-Do](https://support.microsoft.com/zh-TW/office/set-up-microsoft-to-do-490c1a8c-2333-4952-8125-841afadb9620)。

#### <a name="skype-for-business"></a>商務用 Skype

以下是關於如何在商務用 Skype 中存取、檢視和匯出個人資料的一些額外資訊。

- 附加至會議的檔案會在實際會議中保留 180 天，然後就會變成無法存取。會議參與者可以透過從會議邀請加入會議，然後檢視或下載附加檔案的方式，來存取這些檔案。請參閱[預先載入商務用 Skype 會議的附件](https://support.microsoft.com/zh-TW/office/preload-attachments-for-a-skype-for-business-meeting-fd3d9f9d-b448-4754-b813-02e49393f251)中的＜使用會議中的附件＞一節。
- 商務用 Skype 中的交談會保留在使用者信箱中的 [交談記錄] 資料夾內。您可以使用內容搜尋來搜尋信箱，找出 Skype 交談中的資料。
- 資料主體可在商務用 Skype 中匯出其連絡人。若要這麼做，需以滑鼠右鍵按一下商務用 Skype 中的連絡人群組，並按一下 [複製]****。然後，資料主體可以將電子郵件地址的清單，貼入文字或 Word 文件中。
- 如果會議參與者的 Exchange Online 信箱處於訴訟資料暫留狀態，或已指派給 Office 365 保留原則，則附加至會議的檔案會保留在參與者信箱中。若檔案的保留期間尚未過期，您就可以使用「內容搜尋」來搜尋參與者信箱中的檔案。如需保留檔案的詳細資訊，請參閱[保留附加至商務用 Skype 會議的大型檔案](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/retaining-large-files-attached-to-a-meeting)。

## <a name="providing-a-copy-of-personal-data"></a>提供個人資料的複本

找到可能會回應 DSR 的個人資料之後，您與貴組織有權決定要將哪些資料提供給資料主體。例如，您可以提供他們實際文件的複本、經過適當刪減的版本，或您認為適合分享的部分螢幕擷取畫面。對於這些存取要求的每項回應，您都必須擷取一份文件複本，或其他包含回應資料的項目。

當您提供複本給資料主體時，可能需要移除或刪減關於其他資料主體的個人資訊，以及任何機密資訊。

### <a name="using-content-search-to-get-a-copy-of-personal-data"></a>使用內容搜尋來取得個人資料的複本

有兩種方法可使用「內容搜尋」工具，來取得您在執行搜尋後所找到文件或信箱項目的複本。

- 請先預覽搜尋結果，然後再下載文件或項目的複本。這是下載少數項目或檔案的好方法。
- 匯出搜尋結果，然後下載搜尋傳回的所有項目副本。 這個方法雖然較為複雜，卻是下載許多回應 DSR 之項目的理想方法。 實用報表也隨附於匯出搜尋結果。 您可以使用這些報告，以取得每個項目的額外資訊。 **Results.csv** 報告很實用，因為它包含與匯出項目有關的許多資訊，例如，項目的確切位置 (例如，電子郵件的信箱或文件的 URL 或SharePoint Online 和商務用 OneDrive 的清單)。 此資訊可協助您找出項目的擁有者，因為您在 DSR 調查程序期間可能需要連絡他們。 如需匯出搜尋結果時隨附報告的詳細資訊，請參閱[匯出內容搜尋報告](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report)。

#### <a name="preview-and-download-items"></a>預覽及下載項目

執行新的搜尋，或開啟現有的搜尋後，您可以預覽符合搜尋查詢的每個項目，以驗證它與您正在調查的 DSR 相關。 這也包含搜尋結果傳回的 SharePoint 清單和網頁。 如果您需要將原始檔案提供給資料主體，也能下載原始檔案。 在這兩種情況下，您可以取得螢幕擷取畫面，滿足資料主體取得資訊的要求。

某些類型的項目無法預覽。 若項目或檔案類型不支援預覽，您也可以選擇將個別項目下載到本機電腦，或已對應的網路磁碟機或其他網路位置。 您只能預覽[支援的檔案類型](https://docs.microsoft.com/microsoft-365/compliance/content-search)。

若要預覽及下載項目：

1. 在「安全性與合規性中心」內開啟 [內容搜尋]。
2. 如果未顯示結果，請按一下 [預覽結果]****。
3. 請按一下項目來檢視。
4. 按一下 [下載原始檔案]****，將項目下載到本機電腦。您也必須下載無法預覽的項目。

如需預覽搜尋結果的詳細資訊，請參閱[預覽搜尋結果](https://docs.microsoft.com/microsoft-365/compliance/content-search)。

#### <a name="export-and-download-items"></a>匯出及下載項目

您也可以匯出內容搜尋的結果，來取得電子郵件訊息、文件、清單和網頁 (其中包含個人資料) 的複本，但是這個方法比預覽項目更為複雜。請參閱下一節，以取得[匯出內容搜尋結果](#export-and-download-content-using-content-search)的詳細資料。

## <a name="exporting-personal-data"></a>匯出個人資料

「資料可攜性權利」允許資料主體以「結構化、常用、機器可讀取格式」，要求其個人資料的電子複本，以及要求貴組織將這些電子檔案傳輸給另一個資料控制者。Microsoft 以兩種方式支援此權利：

- 提供 Office 365 應用程式，這些應用程式能以原生、機器可讀取且常用的電子格式來儲存資料。 如需 Office 檔案格式的詳細資訊，請參閱[ Office 檔案格式技術文件](https://msdn.microsoft.com/library/office/cc313105(v=office.12).aspx)。
- 可讓貴組織使用原生檔案格式，或可以輕鬆匯出至其他應用程式的格式 (如 CSV、TXT 及 JSON) 匯出資料。

若要滿足 DSR 匯出要求，您可以使用其原生檔案格式匯出 Office 文件，並從其他 Office 365 應用程式中匯出資料。

### <a name="export-and-download-content-using-content-search"></a>使用內容搜尋來匯出及下載內容

匯出內容搜尋的結果時，可將電子郵件項目下載為 PST 檔案或個別郵件 (.msg 檔案)。從 SharePoint Online 和商務用 OneDrive 網站中匯出文件和清單時，會匯出原生檔案格式的複本。例如，SharePoint 清單會匯出為 CSV 檔案，而網頁會匯出為 .aspx 或 html 檔案。

>[!NOTE]
>若要使用內容搜尋從某位使用者 (您要從該使用者的信箱中匯出項目) 的信箱中匯出信箱項目，該使用者需要獲指派 Exchange Online 方案 2 授權。 

若要匯出及下載項目：

1. 在「安全性與合規性中心」內開啟 [內容搜尋]。
2. 請在搜尋彈出式頁面中，按一下 ![下載圖示](../media/o365-dsr_image21.png) [更多]****，然後按一下 [匯出結果]****。 您也可以匯出報告。
3. 完成 [匯出結果]**** 彈出式頁面上的區段。請務必使用捲軸，以檢視所有匯出選項。
4. 回到安全性與合規性中心的內容搜尋頁面，然後按一下 [匯出]**** 索引標籤。
5. 按一下 [重新整理]**** 來更新頁面。
6. 在 [名稱] **** 欄中，按一下您建立的匯出工作。 匯出作業的名稱是加上 **\_Export** 的內容搜尋名稱。
7. 請在匯出彈出式頁面中，按一下 [匯出鍵]**** 下方的 [複製到剪貼簿]****。 您會使用步驟 10 中的這個按鍵來下載搜尋結果
8. 在彈出式頁面的頂端，按一下 ![下載結果](../media/o365-dsr_image21.png) [下載結果]****。
9. 如果系統提示您安裝 **Microsoft Office 365 電子文件探索匯出工具**，請按一下[安裝]****。
10. 在 [電子文件探索匯出工具]**** 中，於適當的方塊中貼上您在步驟 7 中所複製的匯出金鑰。
11. 按一下 [瀏覽]**** 以指定搜尋結果檔案要下載到的位置。
12. 按一下 [開始]**** 將搜尋結果下載至您的電腦。

匯出程序完成時，您可以在本機電腦上檔案所下載到的位置中存取檔案。內容搜尋的結果會下載到以內容搜尋命名的資料夾中。來自網站的內容搜尋文件會複製到名為 **SharePoint** 的子資料夾。信箱項目則會複製到命名為 **Exchange** 的子資料夾。

如需詳細的逐步指示，請參閱[從安全性與合規性中心匯出搜尋結果](https://docs.microsoft.com/microsoft-365/compliance/export-search-results)。

### <a name="downloading-documents-and-lists-from-sharepoint-online-and-onedrive-for-business"></a>從 SharePoint Online 和商務用 OneDrive 下載文件和清單

另一種從 SharePoint Online 和商務用 OneDrive 匯出資料的方式，就是直接從 SharePoint Online 網站或商務用 OneDrive 帳戶下載文件和清單。您必須獲得存取網站權限的指派，然後移至網站，並下載內容。請參閱：

- [從 OneDrive 或 SharePoint 下載檔案和資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)
- [將 SharePoint 清單匯出至 Excel](https://support.office.com/article/export-to-excel-from-sharepoint-bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

對於某些 DSR 匯出要求，您可能會想要允許資料主體自行下載內容。這可讓資料主體前往 SharePoint Online 網站或共用資料夾，然後按一下 [同步處理]****，以同步處理文件庫或所選資料夾中的所有內容。請參閱：

- [讓使用者可以將 SharePoint 檔案與新的 OneDrive 同步處理用戶端同步](https://docs.microsoft.com/sharepoint/let-users-use-new-onedrive-sync-client)
- [將 SharePoint 檔案與新的 OneDrive 同步處理用戶端同步](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-client-6de9ede8-5b6e-4503-80b2-6190f3354a88)

## <a name="deleting-personal-data"></a>刪除個人資料

從組織的客戶資料中移除其個人資料的「抹除的權利」，是 GDPR 中的關鍵保護機制。 移除個人資料包括刪除整個文件或檔案，或刪除文件或檔案內的特定資料 (這會類似本指南中＜修正＞一節所述的動作和程序)。

當您調查或準備刪除個人資料，以回應 DSR 時，以下是一些重要事項，讓您了解如何在 Office 365 中刪除 (和保留) 資料。

- **虛刪除與實刪除：** Office 365 服務中 (例如，Exchange Online、SharePoint Online 和商務用 OneDrive) 有*虛刪除*和*實刪除*的概念，此概念與已刪除項目是否能在尚未從 Microsoft 雲端永久移除之前復原 (通常是在一段有限的時間內) 有關。 在此情況下，虛刪除的項目可在實刪除之前由使用者和/或系統管理員復原 (在一段有限的時間內)。 已經實刪除的項目會標示為已永久移除，並且會由對應的 Office 365 服務處理時清除。 以下是信箱和網站中的項目如何進行虛刪除和實刪除的說明 (無論項目是由資料擁有者還是系統管理員刪除)：

    - **信箱：** 當郵件從 [刪除的郵件] 資料夾刪除或使用者按下 **Shift + Delete** 來刪除郵件時，郵件會虛刪除。 郵件在虛刪除時會移到信箱中的 [可復原的項目] 資料夾。 在此階段，只要刪除的郵件保留期間還沒到期，使用者就可以復原該郵件 (Office 365 中的刪除的郵件保留期間為 14 天，但系統管理員可以將其增加到最長 30 天)。 在保留期間到期後，該郵件就會實刪除，然後移到隱藏的資料夾 (名為「清除」** 資料夾)。 下一次處理信箱時 (信箱每 7 天處理一次)，就會從 Office 365 永久移除 (清除) 郵件。

    - **SharePoint Online 和商務用 OneDrive 網站**：檔案或文件刪除時會移到網站的資源回收筒 (又稱為「第一階段資源回收筒」**(就像 Windows 中的資源回收筒)。 該項目會在資源回收筒中保留 93 天 (Office 365 網站的已刪除項目保留期間)。 該期間過後，該項目就會自動移到網站集合的資源回收筒，也稱為「第二階段資源回收筒」**。 (請注意，有適當權限的使用者或系統管理員也可以從第一階段資源回收筒刪除項目)。 在此階段，項目會變成已虛刪除；其仍可由 SharePoint Online 的網站集合系統管理員或商務用 OneDrive 中的使用者或系統管理員復原。 項目從第二階段資源回收筒 (自動或手動) 刪除時就會變成已實刪除，使用者或系統管理員也無法存取。請注意，第一階段和第二階段資源回收筒的保留期間都是 93 天。也就是說，當項目第一次刪除時，才會開始計算第二階段資源回收筒的保留時間。 因此，這兩種資源回收筒的最長保留時間總計都是 93 天。

>[!NOTE]
>若能了解導致項目虛刪除或實刪除的動作，將協助您決定在回應刪除要求時，如何以符合 GDPR 需求的方式刪除資料。

- **法務保存措施與保留原則：** 在 Office 365 中，可以將信箱和網站設為「保留」狀態。 簡言之，這表示若信箱或網站處於保留狀態，將不會永久移除 (實刪除) 任何項目，直到項目的保留期間到期或移除保留為止。 事關刪除客戶內容以回應 DSR 時，這點很重要；若從處於保留狀態的內容位置中實刪除項目，該項目並不會從 Office 365 中永久移除。 這表示，我們可以合理預期 IT 系統管理員可將其復原。若貴組織在回應 DSR 時的需求或原則，是在 Office 365 中永久刪除資料並使其無法復原；則必須先從信箱或網站移除保留，才能永久刪除 Office 365 中的資料。 貴組織針對回應 DSR 的指導方針，極可能已有適當的程序來判斷特定 DSR 刪除要求或法務保存措施何者優先。 如果您移除了保留以便刪除項目，仍可在刪除項目後重新進行保留。

### <a name="deleting-documents-in-sharepoint-online-and-onedrive-for-business"></a>刪除 SharePoint Online 和商務用 OneDrive 中的文件

遵循本指南＜探索＞一節中的指導方針，找到位於 SharePoint Online 網站或商務用 OneDrive 帳戶中需要刪除的文件後，您需要將必要的權限指派給資料隱私權主管或 IT 系統管理員，他們才能存取網站並刪除文件。 若有必要，也可以指示文件擁有者刪除文件。

以下是從網站中刪除文件的高層級程序。

1. 請移至網站並找出文件。
2. 刪除文件。當您從網站中刪除文件時，此文件會傳送至第一階段資源回收筒。
3. 請移至第一階段資源回收筒 (網站資源回收筒)，並刪除您在上一個步驟中刪除的同一份文件。此文件會傳送至第二階段資源回收筒。**此時，文件已虛刪除**。
4. 請移至第二階段資源回收筒 (即網站集合資源回收筒)，並刪除您從第一階段資源回收筒中刪除的同一份文件。**此時，文件會實刪除。**

>[!IMPORTANT]
>您無法刪除處於保留狀態的網站 (具有 Office 365 的其中一個保留或法務保存措施功能) 上的文件。在 DSR 刪除要求的優先權高於法務保存措施的情況下，您必須先從網站移除保留，然後才能永久刪除文件。

如需詳細程序，請參閱下列主題。

- [從 SharePoint 文件庫中刪除檔案、資料夾或連結](https://support.microsoft.com/zh-TW/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52)
- [刪除項目或清空 SharePoint 網站的資源回收筒](https://support.microsoft.com/zh-TW/office/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e)
- [從網站集合資源回收筒中刪除項目](https://support.microsoft.com/zh-TW/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653)
- [存取及備份先前使用者的資料](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)中的＜存取離職員工的商務用 OneDrive 文件＞一節
- [刪除商務用 OneDrive 中的檔案或資料夾](https://support.office.com/article/Delete-files-or-folders-in-OneDrive-21fe345a-e488-4fa7-932b-f053c1bebe8a)
- [刪除 SharePoint 中的清單](https://support.microsoft.com/zh-TW/office/delete-a-list-in-sharepoint-2a7bca5b-b8fd-4e5b-8f4b-2ac034f3070d)
- [刪除 SharePoint Online 中的清單項目](https://support.office.com/article/delete-list-items-in-sharepoint-online-db722233-4a38-4889-a6cf-4b33fe5c60c0)

### <a name="deleting-a-sharepoint-site"></a>刪除 SharePoint 網站

您可能會判斷回應 DSR 刪除要求的最佳方式是刪除整個 SharePoint 網站，這將刪除位於網站的所有資料。您可以在 SharePoint Online PowerShell 中執行 Cmdlet 來執行此動作。

- 請使用 [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) Cmdlet 來刪除網站，並將其移至 SharePoint Online 資源回收筒 (虛刪除)。
- 請使用 [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) Cmdlet，來永久刪除網站 (實刪除)。

您無法刪除設為電子文件探索保留狀態，或已指派給保留原則的網站。 您必須先從電子文件探索保留或保留原則中移除網站，然後才能將其刪除。

### <a name="deleting-a-onedrive-for-business-site"></a>刪除商務用 OneDrive 網站

同樣地，您可能會判斷要刪除使用者的商務用 OneDrive 網站，以回應 DSR 刪除要求。如果您刪除使用者的 Office 365 帳戶，其商務用 OneDrive 網站會保留 (並可還原) 30 天。30 天後，它會移至 SharePoint Online 資源回收筒 (虛刪除)，然後 93 天後，就會永久刪除 (實刪除)。若要加速此程序，您可以使用 [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) Cmdlet，將商務用 OneDrive 網站移至資源回收筒，然後使用 [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) Cmdlet 來永久刪除。如同 SharePoint Online 中的網站，若您在刪除使用者的帳戶之前，已將使用者的商務用 OneDrive 網站指派給電子文件探索保留或保留原則，則無法刪除該網站。

### <a name="deleting-onedrive-for-business-and-sharepoint-online-experience-settings"></a>刪除商務用 OneDrive 和 SharePoint Online 體驗設定

除了儲存在商務用 OneDrive 帳戶與 SharePoint Online 網站中、使用者所建立的檔案，這些服務將儲存用來啟用各種體驗的使用者相關資訊。 這些是本文件中先前記載的內容。 請參閱[使用內容搜尋電子文件探索工具來回應 DSR](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) 下的[所選應用程式的其他考量事項](#additional-considerations-for-selected-applications)小節，取得如何存取、檢視及匯出商務用 OneDrive 與 SharePoint Online 應用程式的資料。

#### <a name="deleting-a-sharepoint-user-profile"></a>刪除 SharePoint 使用者設定檔

刪除 Azure Active Directory 中的使用者帳戶 30 天後，SharePoint 使用者設定檔將永久刪除。不過，您可以實刪除使用者帳戶，這將會移除 SharePoint 使用者設定檔。如需詳細資訊，請參閱本指南中的[刪除使用者](#deleting-a-user)一節。

系統管理員可以在 SharePoint Online PowerShell 中使用 **Remove-SPOUserProfile** Cmdlet，加速刪除使用者的使用者設定檔。請參閱 [Remove-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserprofile?view=sharepoint-ps)。這會要求至少在 Azure Active Directory 中「虛刪除」使用者。

#### <a name="deleting-user-information-lists-on-sharepoint-online-sites"></a>刪除 SharePoint Online 網站上的使用者資訊清單

對於已從組織離職的使用者，基於 SharePoint 資料行欄位的參考完整性，此資料仍會保留在他們曾經互動過的網站上。系統管理員可以在 SharePoint Online PowerShell 中使用 **Remove-SPOUserInfo** 命令，刪除使用者在特定網站上的所有使用者資訊屬性。如需執行此 PowerShell Cmdlet 的相關資訊，請參閱 [Remove-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserinfo?view=sharepoint-ps)。

根據預設，這個命令會保留使用者的顯示名稱，並刪除屬性，例如：電話號碼、電子郵件地址、技能和專業知識，或從 SharePoint Online 使用者設定檔複製而來的其他屬性。 系統管理員可以使用 **RedactUser** 參數，在使用者資訊清單中指定使用者的替代顯示名稱。 這會影響使用者體驗中幾個部分，並會在查看網站中檔案的歷程記錄時導致資訊流失。

最後，刪減功能並不會從文件中移除所有中繼資料或參照使用者的內容。本指南的[對商務用 OneDrive 和 SharePoint Online 中的內容進行變更](#making-changes-to-content-in-onedrive-for-business-and-sharepoint-online)一節，描述了可達成檔案內容和中繼資料刪減效果的方式。此方法包含下載、刪除，並上傳已刪減的檔案複本。

#### <a name="deleting-onedrive-for-business-experience-settings"></a>刪除商務用 OneDrive 體驗設定

刪除所有商務用 OneDrive 體驗設定及資訊的建議方式，就是在將任何保留的檔案重新指派給其他使用者之後，移除使用者的商務用 OneDrive 網站。系統管理員可以使用 [PowerShell Script](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) 和 [SharePoint 用戶端物件模型 (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) (英文) 命令來刪除這些清單。如需有關設定、儲存方式及刪除方式的詳細資訊，請參閱[刪除商務用 OneDrive 體驗設定](https://docs.microsoft.com/sharepoint/delete-odfb-lists)。

#### <a name="onedrive-for-business-and-sharepoint-online-search-queries"></a>商務用 OneDrive 和 SharePoint Online 搜尋查詢

在商務用 OneDrive 和 SharePoint Online 搜尋體驗中所建立的使用者搜尋查詢，會在使用者建立查詢之後的 30 天自動刪除。

### <a name="deleting-items-in-exchange-online-mailboxes"></a>刪除 Exchange Online 信箱中的項目

您可能需要刪除 Exchange Online 信箱中的項目，才能滿足 DSR 刪除要求。 IT 系統管理員有兩種方法可刪除信箱中的項目，取得魚是否要虛刪除或實刪除目標項目。 無法從 Office 365 永久刪除處於保留狀態下項目中的項目，例如 SharePoint Online 或商務用 OneDrive 網站上的文件。 必須先移除保留，才能刪除項目。 同樣地，您必須決定信箱上的保留狀態或 DSR 刪除要求優先。

#### <a name="soft-delete-mailbox-items"></a>虛刪除信箱項目

您可以使用 [內容搜尋動作] 功能，虛刪除內容搜尋所傳回的項目。 如同先前所述，虛刪除的項目會移至信箱中的 [可復原的項目] 資料夾。

以下是這個程序的簡要概觀：

1. 請建立並執行 [內容搜尋]，來尋找您想要從使用者信箱中刪除的項目。 您可能必須重新執行搜尋以縮小該搜尋結果，以便在搜尋結果中只傳回您想要刪除的項目。
2. 請使用 Office 365 PowerShell 中的 **New-ComplianceSearchAction** **-Purge** 命令，來虛刪除上一個步驟中建立的內容搜尋所傳回的項目。

如需詳細指示，請參閱[搜尋並刪除組織中的電子郵件訊息](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。

#### <a name="hard-delete-mailbox-items"></a>實刪除信箱項目

如果必須實刪除信箱項目以回應 DSR 刪除要求，您可以使用 Exchange Online PowerShell 中的 **Search-Mailbox -DeleteContent** 命令。若您使用這個方法，請考慮使用內容搜尋來開發和精簡搜尋查詢，以便在搜尋中只傳回要刪除的項目。然後，當執行 **Search-Mailbox -DeleteContent** 命令時，您可以使用該查詢語法。

如需詳細指示，請參閱[搜尋並刪除訊息](https://technet.microsoft.com/library/ff459253(v=exchg.150).aspx)。

#### <a name="hard-delete-items-in-a-mailbox-on-hold"></a>實刪除處於保留狀態下信箱中的項目

如同先前所述，如果您實刪除處於保留狀態下信箱中的項目，項目並不會從信箱中移除。而是會移至 [可復原的項目] 資料夾中的隱藏資料夾 ([清除]**** 資料夾)，而且會留在那裡，直到項目的保留期間到期或移除保留為止。若發生了上述任一情況，則下次處理信箱時，項目將從 Office 365 中清除。

貴組織可能會判斷在保留期間到期後永久刪除項目，符合 DSR 刪除要求的需求。不過，如果您判斷必須立即從 Office 365 中清除信箱項目，則必須從信箱中移除保留，然後實刪除信箱中的項目。如需詳細指示，請參閱[刪除處於保留狀態下雲端型信箱的 [可復原的項目] 資料夾中的項目](https://docs.microsoft.com/microsoft-365/compliance/delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold)。

>[!NOTE]
>若要遵循上一個主題中的程序，實刪除信箱項目以滿足 DSR 刪除要求，您可能必須在信箱仍處於保留狀態時虛刪除這些項目，以便將其移至 [可復原的項目] 資料夾。

## <a name="deleting-a-user"></a>刪除使用者

除了刪除個人資料以回應 DSR 刪除要求外，也可以刪除資料主體的使用者帳戶，行使其「被遺忘權」。以下是幾個您可能想要刪除使用者的原因：

- 資料主體已從貴組織離職 (或即將離職)。
- 資料主體已要求您刪除 (針對資料主體所收集的) 由系統所產生的記錄。在系統所產生記錄中的資料，舉例有 Office 365 應用程式和服務使用情況資料、資料主體所執行之搜尋要求的相關資訊，以及作為系統功能與使用者或其他系統互動的產品和服務所產生的資料。如需詳細資訊，請參閱本指南中的[第 3 部分：回應系統所產生記錄的 DSR](#part-3-responding-to-dsrs-for-system-generated-logs)。
- 永久防止資料主體存取或處理 Office 365 中的資料 (與[回應 DSR 限制要求](#responding-to-dsr-restriction-requests)一節中所述的暫時限制存取方法相反)。

刪除使用者帳戶後：

- 使用者再也無法登入 Office 365 或存取貴組織的任何 Microsoft 資源，例如其商務用 OneDrive 帳戶、SharePoint Online 網站或其 Exchange Online 信箱。
- 與使用者帳戶相關聯的個人資料 (例如電子郵件地址、別名、電話號碼和郵寄地址) 都會刪除
- 某些 Office 365 應用程式會移除使用者的相關資訊。 例如，在 Microsoft Flow 中，將從共用流程的擁有者清單中移除已刪除的使用者。
- 系統產生的關於資料主體之記錄 (可能危及服務安全性或穩定性的資料除外)，會在刪除使用者帳戶 30 天後被刪除。 如需詳細資訊，請參閱[刪除系統產生的記錄](#deleting-system-generated-logs)章節一節。

>[!IMPORTANT]
>在您刪除使用者帳戶之後，該使用者將無法登入 Office 365，也無法登入先前用於工作或學校帳戶所依賴的任何產品或服務。如果 Microsoft 是資料控制者，則該使用者也無法直接透過 Microsoft 執行個體來發起任何 DSR 要求。如需詳細資訊，請參閱本指南第 4 部分中的[當 Microsoft 是其資料控制者時，使用組織識別碼來驗證產品和服務](#product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller)一節。

>[!NOTE]
>若您是目前正在進行 FastTrack 移轉的客戶，刪除使用者帳戶並不會將 Microsoft FastTrack 小組所保留的資料複本刪除，其保留之目的僅為完成移轉。如果在移轉期間，您想要 Microsoft FastTrack 小組也一併刪除資料副本，您可以[提交要求](https://go.microsoft.com/fwlink/?linkid=874544)。在一般的業務過程中，完成移轉之後，Microsoft FastTrack 會刪除所有資料副本。

如同上節 (刪除個人資料) 中所述的虛刪除和實刪除資料，當您刪除使用者帳戶時，也會有虛刪除和實刪除狀態。

- 一開始刪除使用者帳戶 (透過刪除系統管理中心或 Azure 入口網站中的使用者) 時，會虛刪除使用者帳戶，並移至 Azure 中的資源回收筒，保留最多 30 天。 此時，使用者帳戶還可以還原。
- 如果永久刪除使用者帳戶，則會實刪除使用者帳戶，並從 Azure 中的資源回收筒移除之。此時，使用者帳戶無法還原，與使用者帳戶相關聯的任何資料也會從 Microsoft 雲端永久移除。實刪除使用者帳戶也會刪除系統產生的關於資料主體之記錄 (可能危及服務安全性或穩定性的資料除外)。

以下是從組織中刪除使用者的高層級程序。

1. 請移至系統管理中心或 Azure 入口網站，然後找出使用者。

2. 刪除使用者。一開始刪除使用者時，該使用者的帳戶會傳送至資源回收筒。此時，只是對使用者進行虛刪除，帳戶會以虛刪除的狀態保留 30 天，這可讓您還原帳戶。30 天後，帳戶會自動實刪除。如需特定指示，請參閱[刪除 Azure AD 中的使用者](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory)。<br><br> 您也可以虛刪除系統管理中心的使用者帳戶。 請參閱[刪除貴組織中的使用者](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)。

3. 如果您不想等待 30 天，再實刪除使用者帳戶，您可以手動進行實刪除。 若要在 Azure 入口網站執行此動作，請移至最近刪除的使用者清單，並永久刪除使用者。 此時使用者會實刪除。 如需指示，請參閱[如何永久刪除最近刪除的使用者](https://docs.microsoft.com/azure/active-directory/active-directory-users-restore)。

您無法實刪除 Office 365 管理入口網站中的使用者。

>[!NOTE]
>在由 21Vianet (中國) 運作的 Office 365 中，您無法如先前所述永久刪除使用者。若要永久刪除使用者，您可以透過位於此 [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage) 的 Office 365 系統管理入口網站來提交要求。移至 [商務]****，然後選取 [訂用帳戶]****  ->  [隱私權]****  ->   [GDPR]****，然後輸入必要的資訊。

### <a name="removing-exchange-online-data"></a>移除 Exchange Online 資料

刪除使用者時要了解的一件事情，就是使用者的 Exchange Online 信箱會發生什麼情況。 在實刪除使用者帳戶 (在上述程序中的步驟 3) 之後，已刪除的使用者信箱並不會從 Office 365 中自動清除。 在使用者帳戶實刪除之後，最多需要 60 天，才會從 Office 365 中永久移除。 以下是在刪除使用者帳戶之後的信箱生命週期，以及在這段時間信箱資料狀態的描述：

- **第 1 天 — 第 30 天** — 可以還原虛刪除的使用者帳戶來完全還原信箱。
- **第 31 天 — 第 60 天** — 在實刪除使用者帳戶後的 30 天內，貴組織中的系統管理員可以復原信箱中的資料，並將其匯入不同的信箱中。 這可讓組織在必要時復原信箱資料。
- **第 61 天 - 第 90 天** - 系統管理員再也無法復原信箱中的資料。 信箱資料將標示為永久移除，並且最多 30 天，信箱資料就會從 Office 365 中清除。

若您判斷此信箱的生命週期不符合貴組織回應 DSR 刪除要求的需求，則在實刪除使用者帳戶「之後**」，您可以[連絡 Microsoft 支援服務](https://support.microsoft.com/)，並要求 Microsoft 手動啟動程序來永久移除信箱資料。 這會永久移除信箱資料的這個程序會在生命週期的第 61 天之後自動啟動，因此在生命週期的這個時間點之後，就沒有理由與 Microsoft 連絡。

## <a name="using-in-app-functionality-to-respond-to-dsrs"></a>使用應用程式內功能來回應 DSR

雖然大部分的客戶資料都是用上節所述的應用程式撰寫及產生，但 Office 365 也會提供許多其他應用程式，讓客戶可以用來產生並儲存客戶資料。不過，內容搜尋目前無法尋找在這些其他 Office 365 應用程式中所撰寫的資料。若要尋找這些應用程式所產生的資料，您或資料擁有者必須使用產品內功能，來尋找可能與 DSR 相關的資料。下表列出這些 Office 365 應用程式。請按一下應用程式圖示，前往本指南中描述如何回應在應用程式中所撰寫資料的 DSR 要求相關章節。

***表 3：其應用程式內功能可用來尋找客戶資料的應用程式***

||||
|:-----:|:-----:|:-----:|:-----:|
| ![Access 圖示](../media/o365-access-64x64.png) <br> [Access](#access) | ![Office 圖示](../media/O365-DSR-Doc_image22.png) <br> [適用於 <br>Office 365 的商務應用程式](#business-apps-for-office-365) | ![Office 圖示](../media/O365-DSR-Doc_image22.png) <br> [教育版](#education)|
| ![流程圖示](../media/o365-flow-64x64.png) <br> [流程](#flow) | ![表單圖示](../media/o365-forms-64x64.png) <br> [表單](#forms) |![Kaizala 圖示](../media/o365-kaizala-64x64.png) <br> [Kaizala](#kaizala) |
| ![Planner 圖示](../media/o365-planner-64x64.png) <br> [Planner](#planner) |![PowerApps 圖示](../media/o365-powerapps-64x64.png) <br> [Power 應用程式](#powerapps) |![Power BI 圖示](../media/o365-powerbi-64x64.png) <br> [Power BI](#power-bi) |
|![Project 圖示](../media/o365-project-64x64.png) <br> [Project](#project-online) |![Publisher 圖示](../media/o365-publisher-64x64.png) <br> [Publisher](#publisher) |![Stream 圖示](../media/o365-stream-64x64.png) <br> [Stream](#stream) |![Sway 圖示](../media/o365-sway-64x64.png) <br> [Sway](#sway) | ![Whiteboard 圖示](../media/O365-DSR-Doc_image36.png) <br> [Whiteboard](#whiteboard) |
|![Yammer 圖示](../media/o365-yammer-64x64.png) <br> [Yammer](#yammer) |
|||

### <a name="access"></a>Access

下列各節說明如何使用 Microsoft Access 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

##### <a name="discover"></a>探索

您有幾種方式可用來在可回應 DSR 要求的 Access 資料庫中搜尋記錄。對於 DSR 調查，您可以搜尋資料主體相關記錄或搜尋含有特定資料的記錄。例如，您可以搜尋或移至資料主體的對應記錄。或者，您可以搜尋含有特定資料的記錄，例如有關資料主體的個人資料。如需詳細資訊，請參閱：

- [在 Access 資料庫中尋找記錄](https://support.microsoft.com/zh-TW/office/find-records-in-an-access-database-705220b7-0255-4ef9-9349-6bd7442d1b7e) 
- [建立簡單的選取查詢](https://support.office.com/article/create-a-simple-select-query-de8b1c8d-14e9-4b25-8e22-70888d54de59)

##### <a name="access"></a>Access

找到 DSR 要求相關的記錄或欄位之後，您可以取得資料的螢幕擷取畫面，或將它匯出至 Excel 檔案、Word 檔案或文字檔案。您也可以建立及列印以記錄來源為基礎的報告，或您為了尋找資料所建立的選取查詢。請參閱：

- [Access 中的報告簡介](https://support.office.com/article/introduction-to-reports-in-access-e0869f59-7536-4d19-8e05-7158dcd3681c)
- [將資料匯出到 Excel](https://support.office.com/article/export-data-to-excel-64e974e6-ae43-4301-a53e-20463655b1a9)
- [將資料匯出到 Word 文件](https://support.microsoft.com/zh-TW/office/export-access-data-to-a-word-document-6e954c8e-2243-4cb9-8544-607e5b7bfc12)
- [將資料匯出到文字檔](https://support.microsoft.com/zh-TW/office/export-data-to-a-text-file-f72dfc38-a8a0-4c5b-8c2c-bf2950814140)

##### <a name="export"></a>匯出

如先前所述，您可以將資料從 Access 資料庫匯出為不同的檔案格式。 您選擇要匯出的檔案格式可能會取決於來自資料主體的特定 DSR 匯出要求。 請參閱[匯入及匯出](https://support.microsoft.com/zh-TW/office/import-and-export-c060505b-d8ac-4499-8879-733e56c6106f)主題清單，其中說明如何以不同的檔案格式匯出 Access 資料。

##### <a name="delete"></a>刪除

您可以刪除整筆記錄，或只是從 Access 資料庫中刪除一個欄位。 從 Access 資料庫中刪除一筆記錄的最快方法，就是以 [資料工作表] 檢視開啟資料表，選取您想要刪除的記錄 (列) 或只選取欄位中的資料，然後按 [刪除]。 您也可以使用您為了尋找資料所建立的選取查詢，然後將它轉換為刪除查詢。 請參閱：

- [從資料庫中刪除一或多筆記錄](https://support.office.com/article/ways-to-add-edit-and-delete-records-5e90a80c-106d-4c55-996e-07d7200980ce)
- [建立並執行刪除查詢](https://support.office.com/article/create-and-run-a-delete-query-6da65fe1-0fc7-4a64-8ef0-c052cd4c3ec5)

### <a name="business-apps-for-office-365"></a>適用於 Office 365 的商務應用程式

本節說明如何在下列各種適用於 Office 365 的商務應用程式中使用應用程式內功能來回應 DSR 要求。

- [Bookings](#bookings)
- [Listings](#listings)
- [Connections](#connections)
- [Outlook Customer Manager](#outlook-customer-manager)
- [Invoicing](#invoicing)

#### <a name="bookings"></a>Bookings

下列各節說明如何使用 Microsoft Bookings 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。 這同時適用於獨立的 Bookings 應用程式和透過商務中心存取時的 Bookings。

Microsoft Bookings 允許系統管理員或使用者或其組織內具有 Bookings 授權的員工設定預約頁面，讓客戶可以排程及變更約會、接收確認電子郵件、更新、取消及提醒電子郵件。企業主及其員工也可以透過 Bookings 代表客戶預約事件。 

以下是客戶、系統管理員或員工所建立的資料類型：

- **客戶、合作夥伴和朋友的連絡資訊** - 這項資料包含名稱、電話號碼、電子郵件地址、地址及附註。

    - 任何人都可以使用 Bookings Web、iOS 及 Android 用戶端，手動建立連絡人。
    
    - 任何人都可以透過 Bookings iOS 和 Android 用戶端，將連絡人從 C1 的行動裝置匯入 Bookings 中。
    
    - 在透過任何預約者的預約工作流程建立預約時，也會自動建立連絡人，不論預約是由使用者代表客戶建立，或是由客戶使用擁有者的預約頁面建立。

- **預約事件** - 企業主或其指定員工與客戶之間會有一些會議，這些會議是由企業主或客戶透過企業主的公用預約頁面所建立。 此資料包括名稱、地址、電子郵件地址、電話號碼，以及企業主在預約時向客戶收集的任何其他資訊。

- **電子郵件確認/取消/更新** - 這些是系統所產生和傳送的特定預約事件相關電子郵件訊息。 其中包含排定要提供相關服務之員工的個人資料，以及包含企業主或客戶在預約時所輸入之客戶的個人資料。

所有客戶內容都會儲存在裝載組織 Bookings 的 Exchange Online 信箱。 除非企業主和客戶明確要求刪除資料，或者如果他們離開服務，只要他們仍在服務中，就會保留此內容。 此內容可以利用產品內 UI、利用 Cmdlet，或是透過刪除相關的預約信箱來刪除。 一旦起始刪除動作，資料就會在企業主設定的期間內刪除。 

如果客戶決定離開服務，其客戶內容會在 90 天後刪除。 如需使用者帳戶刪除後何時會刪除信箱內容的詳細資訊，請參閱[移除 Exchange Online 資料](#removing-exchange-online-data)。

#### <a name="end-user-identifiable-information"></a>使用者識別資訊

使用者識別資訊 (EUII) 包含 Bookings 中已排定員工的相關個人和連絡人資訊。當企業主設定 Bookings 及在設定後進行更新時，此資訊就會新增至員工詳細資料頁面。其中包含員工的名稱、縮寫、電子郵件地址和電話號碼。此資料會儲存在裝載 Bookings 的 Exchange Online 信箱中。

除非已使用應用程式內 UI 明確地刪除企業主或系統管理員，或刪除相關的預約信箱，否則只要員工仍在服務中，都會保留此資料。當系統管理員開始刪除員工的詳細資料時，或者如果員工離職，就會根據企業主或系統管理員所設定的 Exchange Online 信箱內容保留原則，刪除其詳細資料。

##### <a name="discoveraccess"></a>探索/存取

Bookings 會收集並儲存下列類型的資料：

- **企業設定檔資訊：** 使用 Bookings 之企業的相關客戶內容是透過 Bookings 的企業資訊表單來收集，而如果客戶使用 Bookings 搭配商務中心，則此內容就會與商務中心的企業設定檔同步處理。 與此資料相關聯的唯一 EUII 是 C1 的電子郵件地址。 此地址為傳送新預約通知和更新電子郵件的目標。
- **客戶連絡人：** 連絡人可以在 Bookings Web、iOS 和 Android 用戶端中手動建立，也可以從行動裝置匯入。 使用自助服務預約頁面期間也會自動建立連絡人。 它們包含 EUII，並儲存在 Bookings 信箱中。
- **員工詳細資料：** 客戶內容包括有資格提供從 Bookings Web、iOS 或 Android 用戶端建立之服務的員工相關資料。 員工詳細資料可以包含名稱、電子郵件地址和電話號碼。
- **預約事件：** 這些是企業使用 Web 用戶端或 Android/iOS 應用程式所建立，或由客戶使用公用預約頁面 (或 Facebook 頁面) 所建立的客戶會議和相關客戶內容。 這些事件可以包括名稱、地址、電子郵件地址、電話號碼及約會詳細資料。
- **會議要求、電子郵件確認/取消/更新，以及電子郵件提醒：** 這些是由系統傳送的預約相關電子郵件訊息。 其中包含在預約時輸入的員工資料和客戶資料。

##### <a name="export"></a>匯出

若要匯出企業主、員工和客戶的對應資料，您可以使用商務中心隱私權入口網站。請參閱[使用商務中心隱私權入口網站匯出或刪除使用者資料](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8)。

##### <a name="delete"></a>刪除

您可以刪除下列類型的 Bookings 資料，以回應 DSR 刪除要求：

- **企業設定檔資訊和連絡人：** 您可以在系統管理中心刪除 Bookings 信箱。 刪除信箱之後，您可以在 30 天內將它還原。 30 天之後，就會永久刪除帳戶和對應的信箱。 如需刪除使用者帳戶的詳細資訊，請參閱[刪除使用者](#deleting-a-user)一節。
- **員工詳細資料：** 您可以從 Bookings 儀表板中刪除員工。 若要永久刪除員工，您可以刪除其 Office 365 帳戶。
- **Bookings 事件：** 您可以從 Bookings 行事曆中刪除 Bookings 事件，這會移除客戶的資訊。
- **會議要求、電子郵件確認/取消/更新以及電子郵件提醒：** 您可以從 Bookings 行事曆中刪除這些項目，這會移除客戶的資訊。

企業主和系統管理員也可以使用商務中心隱私權入口網站來刪除其客戶的資料。請參閱[使用商務中心隱私權入口網站匯出或刪除使用者資料](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8)。

此外，您可以刪除企業主和員工資料，也可以刪除對應的使用者帳戶。請參閱[刪除使用者](#deleting-a-user)一節。

#### <a name="listings"></a>Listings

下列各節說明如何使用 Microsoft Listings 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

##### <a name="discover"></a>探索

Listings 擁有者可以將其企業連線至 Google、Bing、Yelp，以查看彙總評分和評論檢視。 Listings 會收集並儲存下列類型的資料：

- Google 評論和評分
- Bing 評論和評分
- Yelp 評論和評分
- Facebook 評論和評分

##### <a name="access"></a>存取
Listings 擁有者可以登入 Listings 儀表板來查看其評論和評分。

##### <a name="export"></a>匯出

若要匯出企業主、員工和客戶資料，請使用商務中心隱私權入口網站。請參閱[使用商務中心隱私權入口網站匯出或刪除使用者資料](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8)。

##### <a name="delete"></a>刪除

如果 Listings 擁有者想要刪除其 Listings 資訊，他們可以在 Listings 頁面上中斷與提供者的連線。在他們中斷連線之後，就會刪除其 Listings 資訊。

#### <a name="connections"></a>連線

下列各節說明如何使用 Microsoft Connections 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

##### <a name="discover"></a>探索

Connections 會收集並儲存下列類型的資料： 

- 客戶/連絡人是由企業使用 Web 用戶端或行動裝置應用程式 (iOS、Android) 建立，或在商務連絡人收到電子郵件行銷活動時使用應用程式建立。 客戶資料可以包括名稱、地址、電子郵件地址及稅務識別碼。 所有商務中心應用程式會共用連絡人。
- 客戶可以在 Connections 註冊頁面上進行註冊，並儲存其個人資訊。
- 電子郵件行銷活動中的連結

##### <a name="access"></a>Access

Connections 擁有者可以登入 Connections 儀表板，並查看他們所傳送的電子郵件行銷活動。

##### <a name="export"></a>匯出

若要匯出企業主、員工和客戶資料，請使用商務中心隱私權入口網站。請參閱[使用商務中心隱私權入口網站匯出或刪除使用者資料](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8)。

##### <a name="delete"></a>刪除

在 Connections 擁有者傳送電子郵件行銷活動之後，就無法刪除行銷活動。如果有他們想要刪除的草擬行銷活動，他們可以登入 Connections 儀表板並刪除草稿行銷活動。

#### <a name="outlook-customer-manager"></a>Outlook Customer Manager

下列各節說明如何使用 Outlook Customer Manager 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

##### <a name="discover"></a>探索

Outlook Customer Manager 收集並儲存 Outlook Customer Manager 擁有者及其客戶和商務連絡人的使用者資訊。

- 擁有者資料。這包括名稱、地址及電子郵件地址。擁有者與客戶共用的文件和檔案會儲存在商務用 OneDrive、SharePoint Online 中，以及以工作形式儲存在 Outlook 中。
- 客戶與商務連絡人資料。客戶資料可包括名稱、地址及電子郵件地址。企業在 Outlook 或 Outlook Web 應用程式中建立的客戶和連絡人資料會在商務中心共用。客戶與企業共用的文件和檔案會儲存在商務用 OneDrive、SharePoint Online 中，以及以工作形式儲存在 Outlook 中。

Outlook Customer Manager 也會在 Exchange 中儲存有關客戶的活動和見解。

##### <a name="access"></a>Access

Outlook Customer Manager 擁有者可以登入 Outlook 或 Outlook Web 應用程式，然後移至 Outlook Customer Manager 儀表板來查看他們與其客戶的互動。

##### <a name="export"></a>匯出

若要匯出企業主和客戶資料，請使用 Outlook Customer Manager 隱私權入口網站。如需詳細資訊，請參閱[使用 Outlook Customer Manager 隱私權入口網站匯出或刪除使用者資料](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8)。

##### <a name="delete"></a>刪除

若要刪除客戶資料，請使用 Outlook Customer Manager 隱私權入口網站。請參閱[使用 Outlook Customer Manager 隱私權入口網站匯出或刪除使用者資料](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8)。

#### <a name="invoicing"></a>Invoicing

下列各節說明如何使用 Microsoft Invoicing 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

##### <a name="discover"></a>探索

Invoicing 會收集並儲存下列類型的資料：

- **連絡人：** 這些是由企業在針對客戶/商務連絡人建立發票或估計值時所建立。 連絡人會在商務中心共用。 客戶資料包括名稱、地址、電子郵件地址及稅務識別碼。
- **發票：** 這些會建立並傳送給客戶，其代表負債與應納稅捐。
- **估計值：** 企業也可以將估計值傳送給客戶。 如果客戶接受估計值，它就會轉換成發票。 估計值會在客戶接受之後轉換為發票。 估計值記錄一旦轉換成發票，就不會保存。

##### <a name="access"></a>Access

使用者可以移至其商務中心的 Invoicing 儀表板，以查看他們所建立的發票草稿以及客戶已查看的發票。

##### <a name="export"></a>匯出

若要匯出客戶發票資料，請使用商務中心隱私權入口網站。請參閱[使用商務中心隱私權入口網站匯出或刪除使用者資料](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8)。

##### <a name="delete"></a>刪除

建立並傳送發票之後，因為會計法而無法加以刪除。Invoicing 擁有者可以要求 Microsoft 從 Office 365 中刪除其部分或所有資訊。

或者，您可以在 Office 365 中刪除發票擁有者的使用者帳戶。請參閱[刪除使用者](#deleting-a-user)一節。

### <a name="education"></a>教育版

本節說明如何使用下列 Microsoft 教育版應用程式的應用程式內功能來回應 DSR 要求。

- 作業
- 課程筆記本

#### <a name="assignments"></a>作業

下列各節說明如何使用「作業」中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

##### <a name="discoveraccess"></a>探索/存取

「作業」會儲存教師和學生所產生的資訊。其中有些資訊會儲存在 SharePoint 中，有些會儲存在非 SharePoint 位置。

##### <a name="finding-assignments-data-stored-in-sharepoint"></a>尋找 SharePoint 中儲存的「作業」資料

與作業提交相關聯的學生檔案會儲存在文件庫 (名為**學生功課**) 中，而與教師建立所建立且學生可存取的作業相關聯的檔案則會儲存在不同的文件庫 (名為**課程檔案**) 中。這兩個文件庫都位於對應的課程小組 SharePoint 網站中。

系統管理員可以在安全性與合規性中心使用內容搜尋工具，搜尋與作業提供相關的學生檔案 (在學生功課和課程檔案文件庫中)，以及與作業相關的檔案。 例如，系統管理員可以搜尋組織中的所有 SharePoint 網站，並在搜尋查詢中使用學生的名稱、課程或作業名稱，以尋找與 DSR 要求相關的資料。

同樣地，系統管理員可以針對教師分發給學生的檔案，搜尋與作業相關的教師檔案。 例如，系統管理員可以搜尋組織中的所有 SharePoint 網站，並在搜尋查詢中使用教師的姓名和班級或作業名稱，以尋找與 DSR 要求相關的資料。

如需詳細資訊，請參閱：

- [作業系統管理員文件](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-admin-documentation)
- [使用內容搜尋電子文件探索工具來回應 DSR](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) (本指南中)。

##### <a name="finding-assignments-data-not-stored-in-sharepoint"></a>尋找未儲存在 SharePoint 中的「作業」資料

下列類型的「作業」資料不會儲存在課程小組 SharePoint 網站中，因此無法使用內容搜尋來探索。 此資料包括下列各項：

- 學生的成績和老師的意見反應
- 每個學生針對作業所提交的文件清單
- 作業詳細資料，例如作業到期的日期

若要尋找的資料，系統管理員或教師必須進入課程小組網站中的 [作業]，以找出可能與 DSR 要求相關的資料。系統管理員可以將本身新增為課程的擁有者，並檢視該課程小組的所有作業。

即使學生已經不屬於某個課程，其資料仍可能出現在課程中並標示為「不會再註冊」。 在此情況下，提交 DSR 要求的學生必須將他們正式註冊的課程清單提供給系統管理員。

##### <a name="export"></a>匯出

您可以使用 PowerShell 指令碼取得學生的課程清單，然後使用 PowerShell 指令碼匯出資料，來匯出特定學生已註冊之所有課程的作業資料。 請參閱：

- [設定 Teams 作業](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [取得特定學生的課程清單](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [從「作業」中匯出學生和教師資料](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-export)

如果已從課程小組網站中移除此學生，系統管理員可以在執行匯出指令碼前，先將學生新增回該網站。或者，系統管理員可以使用指令碼的輸入檔，找出學生曾經註冊的每個課程。您也可以使用「作業」匯出指令碼來匯出教師有權存取之所有作業的提交資料。

##### <a name="delete"></a>刪除

您可以使用 PowerShell 指令碼取得學生的課程清單，然後使用 PowerShell 指令碼刪除資料，來刪除特定學生已註冊之所有課程的作業資料。 您應在從課程中移除學生之前這麼做。 請參閱：

- [設定 Teams 作業](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [取得特定學生的課程清單](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [從「作業」中刪除學生資料](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-delete)

如果已從課程小組網站中移除此學生，系統管理員可以在執行匯出指令碼前，先將學生新增回該網站。或者，系統管理員可以使用指令碼的輸入檔，找出學生曾經註冊的每個課程。您無法使用「作業」刪除指令碼來刪除教師資料，因為在課程小組網站中會共用所有的作業。此外，系統管理員必須將本身新增至課程小組，然後刪除特定作業。

#### <a name="class-notebook"></a>課程筆記本

稍早已在本指南中討論如何在課程筆記本中搜尋內容。 請參閱 [OneNote 課程筆記本](#onenote-class-notebook)一節。 您也可以使用「 內容搜尋 」工具匯出課程筆記本中的資料。 此外，系統管理員或資料主體也可以匯出課程筆記本中的資料。 請參閱[儲存課程筆記本複本](https://support.office.com/article/44733e18-0ef1-4d4b-be51-fc2ac5bfe9ec)。

### <a name="flow"></a>Flow

下列各節說明如何使用 Microsoft Flow 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索

人員可以使用 Flow 來執行資料相關工作，例如同步處理應用程式之間的檔案、將某個 Office 365 服務中的檔案複製到另一個服務，以及從某個 Office 365 應用程式中收集資料，並將其儲存在另一個服務中。例如，使用者可設定一個 Flow，以將 Outlook 電子郵件附件儲存至其商務用 OneDrive 帳戶。在此範例中，您可以使用「內容搜尋」工具來搜尋使用者信箱，以找出包含附件的電子郵件訊息，或搜尋其商務用 OneDrive 帳戶，以找出檔案。在以下範例中，您可在 Flow 工作流程所連接的 Office 365 服務中，探索 Flow 所處理的資料。

此外，人員可以使用 Flow，將 Office 365 中的檔案複製或上傳至外部服務，例如 Dropbox。在這些情況下，有關外部服務中資料的 DSR 要求必須提交給外部服務；因為在這類案例中是由外部服務來處理這些資料。

如果系統管理員收到 DSR 要求，可以將自己新增為使用者流程的擁有者。 這可讓系統管理員執行匯出流程定義、執行歷程記錄，以及執行流程權限重新指派等功能。 請參閱[管理系統管理中心內的流程](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)。

系統管理員需要具有下列權限的帳戶，才能夠將自己新增為 Flow 的擁有者：

- Flow/PowerApps 方案 2 授權 (付費或試用版)

- [全域系統管理員\ ](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

    或

- [Azure Active Directory 全域系統管理員](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

要具有這些權限，才可讓系統管理員使用 Flow 系統管理中心存取組織中的所有流程。

若要將自己新增為流程的擁有者：

1. 請移至 <https://admin.flow.microsoft.com>
2. 使用您的 Office 365 認證來登入。
3. 在 [環境]**** 頁面上，按一下您想要存取之流程的環境。 請注意，組織具有預設環境。
4. 在所選環境的頁面上，按一下 [資源]****，然後按一下 [流程]****。環境中所有流程的清單隨即顯示。
5. 針對您想要將自己新增為其成員的流程，按一下 [檢視詳細資料]****。
6. 在 [擁有者]**** 底下，按一下 [管理共用]****。
7. 在 [共用]**** 彈出式視窗中，將自己新增為成員，然後儲存變更。

在使自己成為擁有者之後，請移至 [流程]**** \> [我的流程]**** \> [小組流程]****，來存取流程。 您可以從那裡下載執行歷程記錄或匯出流程。 請參閱：

- [下載流程執行歷程記錄](https://flow.microsoft.com/blog/download-history-recurrence/)
- [使用封裝跨環境匯出和匯入您的流程](https://flow.microsoft.com/blog/import-export-bap-packages/)

#### <a name="access"></a>存取

使用者可以存取其流程的定義和執行歷程記錄。

- **流程定義：** 使用者可以匯出流程的定義 (將其匯出為流程套件，並以壓縮檔案形式格式化為 JSON)。 請參閱[使用封裝跨環境匯出和匯入您的流程](https://flow.microsoft.com/blog/import-export-bap-packages/)。
- **流程執行歷程記錄：** 使用者可下載其各個流程的執行歷程記錄。 流程執行歷程記錄下載格式為 CSV 檔案，可在 Excel 中開啟進行篩選或搜尋。 使用者也可以下載多個流程的執行歷程記錄。 請參閱[下載流程執行歷程記錄](https://flow.microsoft.com/blog/download-history-recurrence/)。

#### <a name="delete"></a>刪除

系統管理員可以在 Flow 管理中心將自身新增為使用者流程的擁有者。 如果有使用者離開您的組織且其 Office 365 帳戶已刪除，以其為唯一擁有者的流程仍會保留。 這是為了協助貴組織將流程移轉給新的擁有者，避免對貴公司業務造成影響，尤其是共用商務程序可能會用到的流程。 系統管理員接著需要判斷是否要刪除使用者所擁有的流程，或將該流程重新指派給新的擁有者，並採取行動。

若為共用流程，使用者從貴組織刪除時，其名稱也會從擁有者清單中移除。

#### <a name="export"></a>匯出

系統管理員可以匯出使用者流程的定義和執行歷程記錄。若要這樣做，系統管理員必須在 Flow 系統管理中心，將自己新增為使用者流程的擁有者。

- **流程定義：** 在系統管理員將自己新增為流程的擁有者後，可以移至 **[流程]** \>**[我的流程]** \> ** [小組流程]**，來匯出流程定義 (將其匯出為流程套件，並以壓縮檔案形式格式化為 JSON)。 請參閱[使用封裝跨環境匯出和匯入您的流程](https://flow.microsoft.com/blog/import-export-bap-packages/)。

- **流程執行記錄：** 同樣地，系統管理員必須將自己新增為流程的擁有者，才能匯出流程執行歷程記錄。 流程執行歷程記錄下載格式為 CSV 檔案，這表示您可使用 Excel 進行篩選或搜尋。 只要您具有擁有全，也可下載多個流程的執行歷程記錄。 請參閱[下載流程執行歷程記錄](https://flow.microsoft.com/blog/download-history-recurrence/)。

#### <a name="connections-and-custom-connectors-in-flow"></a>Flow 中的連線和自訂連接器

[連線] 需要使用者提供認證，才能連線至 API、SaaS 應用程式，以及自訂開發系統。 這些連線是由建立連線的使用者所擁有，並可在產品內[管理](https://docs.microsoft.com/flow/add-manage-connections)。 在重新指派 Flows 之後，系統管理員可以使用 PowerShell Cmdlet，在刪除使用者資料的過程中列出並刪除這些連線。

自訂連接器可讓組織連線至現成連接器無法使用的系統，來擴充 Flow 的功能。 自訂連接器作者可將其連接器與組織中的其他人[共用](https://docs.microsoft.com/flow/register-custom-api)。 在收到 DSR 刪除要求後，系統管理員應該考慮重新指派這些連接器的擁有權，以避免業務中斷。 若要加快此程序，系統管理員可以使用 PowerShell Cmdlet，來列出、重新指派或刪除自訂連接器。

### <a name="forms"></a>表單

下列各節說明如何使用 Microsoft Forms 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索

Forms 使用者可以移至 <https://forms.office.com>，然後選取 [我的表單]****，以查看他們所建立的 Forms。他們也可以選取 [與我共用]****，來檢視其他人透過連結所共用的 Forms。如果有許多要排序的 Forms，使用者可以使用產品內搜尋列，依標題或作者搜尋 Forms。若要判斷 Microsoft Forms 是否為可回應 DSR 的個人資料所在的位置，您可以要求資料主體搜尋其 [與我共用]**** 清單，來判斷哪些使用者 (「Forms 擁有者」) 已將 Forms 傳送給資料主體。然後，您可以要求表單擁有者選取導覽列上方的 [共用]****，並將特定表單的連結傳送給您，讓您可以檢視，並進一步判斷該表單對 DSR 是否重要。

#### <a name="access"></a>Access

在找到相關表單之後，您可以按一下 [回應]**** 索引標籤，來存取表單的回應。深入了解如何[檢查您的測驗結果](https://support.microsoft.com/zh-TW/office/check-and-share-your-quiz-results-c4a9b45c-d62f-4eb7-b5db-ad81892c7c07)或[表單結果](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)。 若要在 Excel 中檢視回應結果，請選取 [回應] **** 索引標籤，然後按一下 [在 Excel 中開啟]****。 如果您想要將表單的複本傳送給資料主體，可以取得以 RTF 格式顯示在應用程式中之相關問答的螢幕擷取畫面，或將結果的 Excel 複本傳送給資料主體。 如果您正在使用 Excel，且只想要與資料主體共用問卷結果的一部分，可以刪除特定列或欄，或刪減剩餘的區段，然後共用結果。 或者，您也可以移至 [共用]**\> [取得複製的連結]** (在 [共用] 下的範本)，以便將整個表單的複寫提供給資料主體。

#### <a name="delete"></a>刪除

擁有者可以永久刪除任何問卷、測驗、問卷調查或投票。如果您想要接受「忘記我」DSR 並刪除整個表單，請尋找表單清單中的表單、在表單預覽視窗右上角選取一連串的點 (省略符號)，然後按一下 [刪除]****。表單一經刪除，便無法擷取。如需詳細資訊，請參閱[刪除表單](https://support.microsoft.com/zh-TW/office/delete-a-form-2207e468-ce1b-4c4a-a256-caf631d87af0)。

#### <a name="export"></a>匯出

若要將表單問題和回應匯出至 Excel 檔案，請開啟表單、選取 [回應]**** 索引標籤，然後選取 [在 Excel 中開啟]****。

### <a name="kaizala"></a>Kaizala

下列各節說明如何使用 Microsoft Kaizala 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索

系統管理員可從 Kaizala 管理入口網站存取使用者的組織資料 (也就是在組織群組共用的資料)。組織資料的保留期間是由貴組織的保留原則所決定。除了使用者資料，Kaizala 伺服器也會儲存下列類型的組織資料：

- 屬於組織群組的成員清單
- 組織群組訊息資料，也就是整個組織群組共用的訊息和回應
- 組織中的使用者清單
- 針對組織中所有使用者擷取的產品和服務使用情況資料。
- 組織所建立的 Kaizala 動作
- Kaizala 連接器資料

資料主體可以使用適用於消費者資料的 Kaizala 行動裝置應用程式來存取使用者的消費者資料。消費者資料包括下列類型的資料：

- 屬於 Kaizala 上私人群組的資料 (儲存在 Kaizala 伺服器上 90 天)
- 使用者的設定檔資訊，以及使用者的連絡人
- 與使用者屬於相同群組的成員清單
- 各群組共用的群組訊息和回應
- 使用者的連絡人清單 (儲存於 Kaizala 服務)
- 使用者在 Kaizala 上所進行的交易 (僅適用於印度的 Kaizala 使用者)
- 使用者的產品和服務使用情況資料

#### <a name="access"></a>Access

Kaizala 使用者可以移至其行動裝置，查看他們在其裝置上所建立的 Kaizala 內容。若要判斷 Kaizala 行動裝置應用程式是否為可回應 DSR 的個人資料所在位置，您可以要求資料主體在其 Kaizala 應用程式中搜尋所要求的資訊。

#### <a name="export"></a>匯出

當貴組織中的使用者使用 Kaizala 時，就會產生消費者資料，而如果使用者參與組織群組，則可能會產生組織資料。系統管理員可以從 Kaizala 管理入口網站匯出使用者的組織資料。Kaizala 消費者使用者可以從 Kaizala 行動裝置應用程式匯出其私人資料。在這兩種情況下，請注意，當系統管理員或使用者匯出 Kaizala 資料時，也會匯出產品和服務使用情況資料。如需詳細資訊，請參閱：

- [在 Kaizala 中匯出或刪除使用者的組織資料](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [在 Kaizala 行動應用程式中匯出或刪除您的資料](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

#### <a name="delete"></a>刪除

Kaizala 系統管理員可以在 Kaizala 管理入口網站中移除 Kaizala 使用者的帳戶。刪除使用者帳戶之後，就會從屬於貴組織的所有群組中移除使用者，並從他們的裝置中刪除組織資料。 

若要從使用者的行動裝置移除所有私人資料，Kaizala 使用者可以刪除其 Kaizala 帳戶。刪除帳戶之後，就會從裝置中刪除所有相關的 Kaizala 內容，包括聊天、相片和其他資料。

如需詳細資訊，請參閱：

- [在 Kaizala 中匯出或刪除使用者的組織資料](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [在 Kaizala 行動應用程式中匯出或刪除您的資料](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

### <a name="planner"></a>Planner

下列各節說明如何使用 Microsoft Planner 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索

Planner 計劃與 Microsoft 365 群組相關聯，而且 Microsoft 365 群組的檔案會儲存在該群組的相關聯 SharePoint Online 網站中。 這表示，您可以使用內容搜尋來搜尋 Microsoft 365 群組的網站，以尋找 Planner 檔案。 若要這麼做，您必須要有 Microsoft 365 群組的 URL。 如需如何取得 Microsoft 365 群組之相關資訊的提示，請參閱「Office 365 中的內容搜尋」說明主題中的[搜尋 Microsoft Teams 和 Microsoft 365 群組](https://docs.microsoft.com/microsoft-365/compliance/content-search)，來協助您在對應的 SharePoint Online 網站中搜尋 Planner 檔案。

#### <a name="access"></a>Access

如先前所解說，您可以搜尋與方案相關聯的基礎 SharePoint Online 網站和信箱。 然後您可以預覽或下載相關的搜尋結果以存取資料。

#### <a name="delete"></a>刪除

您可以提供自己存取使用者所屬方案的權限，或以該使用者身分登入來進行變更，而手動刪除使用者的個人資訊。請參閱[刪除 Microsoft Planner 中的使用者資料](https://support.office.com/article/delete-user-data-in-microsoft-planner-4349ded2-1891-4896-8e27-05fd40f3929f)。

#### <a name="export"></a>匯出

您可以使用 PowerShell 指令碼，從 Planner 匯出使用者的資料。匯出資料時，會針對使用者所屬的每個計劃匯出 JSON 檔案。請參閱[從 Microsoft Planner 匯出使用者資料](https://support.office.com/article/export-user-data-from-microsoft-planner-91258c96-b353-4da1-b6d9-d78e4809cf08)。

### <a name="power-bi"></a>Power BI

下列各節說明如何使用 Microsoft Power BI 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索
您可以在 Power BI 中搜尋不同工作區中的內容，包括儀表板、報告、活頁簿和資料集。每種類型的工作區都包含一個搜尋欄位，您可用來搜尋該工作區。請參閱[在 Power BI 服務中搜尋、尋找及排序內容](https://docs.microsoft.com/power-bi/service-navigation-search-filter-sort)。

#### <a name="access"></a>Access

您可以從 Power BI 中的報告列印儀表板、報告及視覺效果，以取得實體複本。 您無法列印整份報告；一次只能列印一頁。 若要這麼做，請移至報告、使用搜尋欄位來尋找特定資料，然後列印該頁面。 請參閱[從 Power BI 服務中列印](https://docs.microsoft.com/power-bi/service-print)。

#### <a name="delete"></a>刪除

若要刪除儀表板、報告和活頁簿，請參閱[幾乎刪除 Power BI 服務中的一切](https://docs.microsoft.com/power-bi/service-delete)。

刪除儀表板、報告或活頁簿並不會刪除基礎資料集。因為 Power BI 依賴與基礎來源資料的即時連線，才能完整且精確，所以必須在基礎來源資料中刪除個人資料。(例如，如果您建立了連線至 Dynamics 365 for Sales 的 Power BI 報告，作為即時資料來源，則您必須在 Dynamics 365 for Sales 中對資料進行所有更正。)

刪除資料之後，您可以使用 Power BI 中[排定的資料重新整理](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh)功能，來更新儲存在 Power BI 的資料集；在此之後，刪除的資料將不再反映在運用該資料的任何 Power BI 報告或儀表板中。 為了符合 GDPR 需求，您應該設有適當的原則，以確保能用適當的步調重新整理您的資料。

#### <a name="export"></a>匯出

為了促成資料可攜性要求，您可以匯出 Power BI 中的儀表板和報告：

- 您可以將儀表板和報告的資料匯出至靜態 Excel 檔案。請參閱[從 Power BI 服務中列印](https://docs.microsoft.com/power-bi/service-print)內的影片。然後，您可以使用 Excel，編輯要包含在可攜性要求中的個人資料，並以常用的、機器可讀取的格式 (例如 .csv 或 .xml) 來儲存。
- 如果 Office 365 中的 Power BI 服務原先是用 Power BI Desktop 發佈的，您就可以從將報告匯出 (下載) 至 .pbix 檔案。然後，您可以將此檔案匯入至 Power BI Desktop，並發佈 (匯出) 至另一個組織的 Power BI 服務中。請參閱[將報告從 Power BI 服務匯出至 Desktop](https://docs.microsoft.com/power-bi/service-export-to-pbix)。

### <a name="powerapps"></a>PowerApps

下列各節說明如何使用 Microsoft Power Apps 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。 下列步驟概述系統管理員如何將應用程式及其相關資源移轉給新的擁有者，以限制業務中斷。

#### <a name="discover"></a>探索

PowerApps 是一種服務，用於組建可在貴組織內共用及使用的應用程式。 在組建或執行應用程式時，使用者最終會將多種類型的資源和資料儲存在 PowerApps 服務中，包括應用程式、環境、連線、自訂連接器和權限。

若要促成與 PowerApps 相關的 DSR 要求，您可以運用 [PowerApps 系統管理中心](https://admin.powerapps.com/)和 [PowerApps Admin PowerShell Cmdlet](https://go.microsoft.com/fwlink/?linkid=871804) 中公開的系統管理作業。 要存取這些工具將需要具有下列權限的帳戶：

- 付費的 PowerApps 方案 2 授權或 PowerApps 方案 2 試用版授權。 您可以在[這裡](https://web.powerapps.com/trial)註冊 30 天試用版授權。
- [全域系統管理員](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)，或
- [Azure Active Directory 全域系統管理員](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

如需尋找個人資料的詳細資訊，請參閱[探索 PowerApps 個人資料](https://go.microsoft.com/fwlink/?linkid=871880)。

PowerApps 服務也包含了 Common Data Service For Apps，可讓使用者可以將資料儲存在 Common Data Service 資料庫內的標準和自訂實體中。 您可以從 [PowerApps Maker 入口網站](https://web.powerapps.com)中檢視儲存在這些實體中的資料，並使用[進階尋找](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)的產品內搜尋功能，來搜尋實體中的特定資料。 如需在 Common Data Service 中探索個人資料的詳細資料，請參閱[探索 Common Data Service 個人資料](https://go.microsoft.com/fwlink/?linkid=871881)。

#### <a name="access"></a>Access

系統管理員可以使用 [PowerApps 系統管理中心](https://admin.powerapps.com/)或 [PowerApps Admin PowerShell Cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)，將存取和執行應用程式及相關聯資源 (包括流程、連線及自訂連接器) 的權限指派給自己。

在有權存取使用者的應用程式之後，您可以使用網頁瀏覽器來開啟應用程式。在開啟應用程式之後，您可以取得資料的螢幕擷取畫面。請參閱[在網頁瀏覽器中使用 PowerApps](https://docs.microsoft.com/powerapps/run-app-browser)。

#### <a name="delete"></a>刪除

因為 PowerApps 可讓使用者組建企業營運應用程式，此應用程式可能是貴組織的關鍵部分，當使用者從貴組織離職且其 Office 365 帳戶遭到刪除時，系統管理員必須決定要刪除使用者所擁有的應用程式，還是只重新指派給新的擁有者。 這是為了協助貴組織將應用程式移轉給新的擁有者，並避免可能用於共用業務流程的應用程式造成業務中斷。

對於共用資料 (例如應用程式)，系統管理員必須決定要永久刪除該使用者的共用資料，還是將此資料重新指派給自己或其組織內的其他人，來加以保留。 請參閱[刪除 PowerApps 個人資料](https://go.microsoft.com/fwlink/?linkid=871883)。

使用者儲存在 Common Data Service For Apps 資料庫中實體的任何資料，也會需要由系統管理員檢閱；且必要時，使用產品內功能刪除這些資料。請參閱[刪除 Common Data Service 使用者個人資料](https://go.microsoft.com/fwlink/?linkid=871886)。

#### <a name="export"></a>匯出

系統管理員可以使用 [PowerApps 系統管理中心](https://admin.powerapps.com/)和 [PowerApps Admin PowerShell Cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)，針對 PowerApps 服務內的使用者，匯出所儲存的個人資料。請參閱[匯出 PowerApps 個人資料](https://go.microsoft.com/fwlink/?linkid=871883)。

您也可以使用[進階尋找](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)的產品內搜尋功能，搜尋任何實體中的使用者個人資料。如需匯出 Common Data Service 中個人資料的詳細資料，請參閱[匯出 Common Data Service 個人資料](https://go.microsoft.com/fwlink/?linkid=871889)。

#### <a name="connections-and-custom-connectors-in-powerapps"></a>PowerApps 中的連線和自訂連接器

[連線] 需要使用者提供認證，才能連線至 API、SaaS 應用程式，以及自訂開發系統。 這些連線是由建立連線的使用者所擁有，並可在產品內[管理](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection)。 在重新指派 PowerApps 之後，系統管理員可以使用 PowerShell Cmdlet，在刪除使用者資料的過程中列出並刪除這些連線。

自訂連接器可讓組織連線至現成連接器無法使用的系統，來擴充 PowerApps 的功能。 自訂連接器作者可將其連接器與組織中的其他人[共用](https://docs.microsoft.com/connectors/custom-connectors/use-custom-connector-powerapps)。 在收到 DSR 刪除要求後，系統管理員應該考慮重新指派這些連接器的擁有權，以避免業務中斷。 若要加快此程序，系統管理員可以使用 PowerShell Cmdlet，來列出、重新指派或刪除自訂連接器。

### <a name="project-online"></a>Project Online

下列各節說明如何使用 Microsoft Project Online 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover-and-access"></a>探索和存取

您可以使用「內容搜尋」來搜尋與 Project 相關聯的 SharePoint Online 網站 (第一次建立 Project 時，會有一個選項用來建立相關聯的 SharePoint Online 網站)；內容搜尋不會搜尋 Project Online 中實際專案內的資料，只會搜尋相關聯的網站。 雖然「內容搜尋」會搜尋專案的中繼資料，例如主體中提及的人員，不過，這可能有助於您尋找 (和存取) 包含與 DSR 相關資料的專案。

>[!TIP]
>貴組織中網站集合的 URL，其中與專案相關聯的網站為 **https://\<貴組織網址\>.sharepoint.com/sites/pwa**；例如，**https://contoso.sharepoint.com/pwa**。您可以使用這個特定的網站集合，作為內容搜尋的位置，然後作為搜尋查詢中專案的名稱。此外，IT 系統管理員也可以使用 SharePoint 系統管理中心的網站集合頁面，取得組織中 PWA 網站集合的清單。

#### <a name="delete"></a>刪除

您可以從 Project Online 環境中刪除使用者的相關資訊。請參閱[從 Project Online 中刪除使用者資料](https://support.office.com/article/delete-user-data-from-project-online-252fa593-9c25-47ed-b861-643fe8bf1cb7)。

#### <a name="export"></a>匯出

您可以從 Project Online 環境中匯出特定使用者的內容。此資料會以 JSON 格式匯出至多個檔案。如需逐步指示，請參閱[從 Project Online 中匯出使用者資料](https://support.office.com/article/export-user-data-from-project-online-27f3838d-3dbe-4b98-80dc-df55f851154d)。如需匯出之檔案的詳細資訊，請參閱 [Project Online 匯出 json 物件定義](https://support.office.com/article/project-online-export-json-object-definitions-ce5faeae-9af4-4696-b847-a1f4f20327c7)。

### <a name="publisher"></a>Publisher

下列各節說明如何使用 Microsoft Publisher 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索

您可以使用應用程式內的搜尋功能，以您在大部分 Office 應用程式的相同方式，來尋找 Publisher 檔案中的文字。 請參閱[尋找及取代文字](https://support.office.com/article/find-and-replace-text-bfe54275-b7c7-4d0f-904d-a2f38d322268)。

#### <a name="access"></a>Access

找到資料之後，就可以取得其螢幕擷取畫面，或複製資料並貼到 Word 或文字檔案，並將該資料提供給資料物件。 您也可以將出版物儲存為 Word、PDF 或 XPS 檔案。 請參閱：

  - [將出版物儲存為 Word 文件](https://support.microsoft.com/zh-TW/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [使用 Publisher 將出版物另存新檔為或轉換為 .pdf 或 .xps](https://support.microsoft.com/zh-TW/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="export"></a>匯出

您可以使用實際 Publisher 檔案提供資料主體，或如先前所述，您可以將出版物另存新檔為 Word、PDF 或 XPS 檔案。 請參閱：

  - [將出版物儲存為 Word 文件](https://support.microsoft.com/zh-TW/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [使用 Publisher 將出版物另存新檔為或轉換為 .pdf 或 .xps](https://support.microsoft.com/zh-TW/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="delete"></a>刪除

您可以刪除出版物中的內容、刪除整個頁面，或刪除整個 Publisher 檔案。 請參閱[新增或刪除頁面](https://support.office.com/article/add-or-delete-pages-daf71e39-86e0-4bbc-a186-d5ec70450b08)。

### <a name="stream"></a>Stream

下列各節說明如何使用 Microsoft Stream 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索

若要探索已產生或上傳至 Stream 並可能與資料主體要求相關的內容，系統管理員可以執行使用者報告，判斷 Stream 使用者可能已上傳、建立或張貼哪些影片、影片描述、群組、頻道或評論。 如需如何產生報告的指示，請參閱[在 Microsoft Stream 中管理使用者資料](https://docs.microsoft.com/stream/managing-user-data)。 報告輸出為 HTML 格式，包含可用來瀏覽到可能感興趣影片的超連結 。如果您想要檢視具有自訂權限集的影片，而且您不屬於影片訴求對象的原始使用者，您可以用系統管理模式檢視，請參閱 [Microsoft Stream 中的系統管理員功能](https://docs.microsoft.com/stream/manage-content-permissions)。  

#### <a name="access"></a>Access

根據資料主體要求的本質，上述的報告有助於滿足資料主體要求。使用者報告包括 Stream 使用者的名稱和唯一識別碼、使用者上傳的影片清單、使用者可存取的影片清單、使用者建立的頻道清單、使用者所屬的所有群組清單，以及使用者對影片留下的所有評論清單。這份報告更進一步顯示該使用者是否已檢視使用者報告中所列的每部影片。如果您想要將影片存取權提供給資料主體以滿足 DSR 要求，您可以共用該影片。

#### <a name="export"></a>匯出

請參閱 Stream 的「存取」一節。 

#### <a name="delete"></a>刪除

若要刪除或編輯影片或任何其他 Stream 內容，Stream 系統管理員可以選取用系統管理模式檢視，以執行所需的功能。請參閱 [Microsoft Stream 中的系統管理員功能](https://docs.microsoft.com/stream/manage-content-permissions)。如果使用者已離開組織，而且希望移除其名稱，使其不要出現在其上傳影片的旁邊，您可以移除他們的名稱或以另一個名稱取代之。請參閱[在 Microsoft Stream 中管理已刪除的使用者](https://docs.microsoft.com/stream/managing-deleted-users)。

### <a name="sway"></a>Sway

下列各節說明如何使用 Microsoft Sway 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索

只有擁有者和經過作者允許的人員，才能檢視使用 Sway 所建立的內容 (可在 [www.sway.com](https://www.sway.com) 找到)。 請參閱 [Sway 的隱私權設定](https://support.office.com/article/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217)。 若要判斷 Sway 是否為可回應 DSR 的個人資料可能存在的位置，您可以要求資料主體和可能產生資料主題相關內容的組織使用者搜尋其 Sway，並與您共用可能包含可回應資料主體要求之個人資料的任何 Sway。 如需如何共用 Sway 的相關資訊，請參閱[共用您的 Sway](https://support.office.com/article/share-your-sway-1cf853b8-ef7e-46b0-b704-003e58d28998) 一文中的＜從您的組織帳戶共用 Sway＞。

#### <a name="access"></a>Access

如果您在 Sway 中找到想要與資料主體共用的個人資料，可讓資料主體透過下列幾種方式之一存取資料。 您可以將 Sway 線上版本的複本提供給資料主體 (如上述)；也可以針對 Sway 中想共用的相關部分，取得幕擷取畫面；或者將 Sway 列印出來、下載至 Word 中，或將其轉換為 PDF 檔案。 下方的＜匯出＞一節會進一步說明如何下載 Sway。

#### <a name="delete"></a>刪除

若要了解如何刪除 Sway，請移至 [Sway 的隱私權設定](https://support.office.com/article/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217)中的＜如何刪除我的 Sway？＞一節。

#### <a name="export"></a>匯出

若要匯出 Sway，請開啟您想要下載的 Sway、在左上角選取一連串的點 (省略符號)、選取 [匯出]****，然後選擇 [Word]**** 或 [PDF]****。

### <a name="whiteboard"></a>Whiteboard

下列各節說明如何使用 Microsoft Whiteboard 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

- [Surface Hub 上的 Whiteboard 2016](#whiteboard-2016-on-surface-hub)
- [其他所有平台上的 Whiteboard](#whiteboard-for-pc-surface-hub-and-other-platforms)

#### <a name="whiteboard-2016-on-surface-hub"></a>Surface Hub 上的 Whiteboard 2016

本節說明如何針對在 Surface Hub 上使用內建 Whiteboard 2016 應用程式建立的資料來回應 DSR 要求。

##### <a name="discover"></a>探索

Whiteboard 檔案 (.wbx 檔案) 會儲存在使用者的商務用 OneDrive 帳戶中。如果他們建立的白板可能包含可回應 DSR 要求的個人資料，您可以詢問資料主體或其他使用者。他們可以與您共用白板，您也可以取得其複本來提供給資料主體。

若要存取及移轉白板： 

1. 授與您自己存取使用者之商務用 OneDrive 帳戶的權限。請參閱[存取及備份先前使用者的資料](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)中的＜存取離職員工的商務用 OneDrive 文件＞一節。
2. 移至使用者的商務用 OneDrive 帳戶中的 [Whiteboard 應用程式資料] 資料夾，並且複製您要移轉之白板的 .wbx 檔案。
3. 授與您自己存取資料主體之商務用 OneDrive 帳戶的權限，然後移至 [Whiteboard 應用程式資料] 資料夾。
4. 貼上您在上一步中複製的 .wbx 檔案。

##### <a name="access"></a>Access

如果您在可回應 DSR 存取要求的白板中尋找個人資料，您可以用下列幾種方式提供白板的資料主體存取權：

- 取得白板相關部分的螢幕擷取畫面。
- 將 .wbx 檔案的複本上傳到資料主體的商務用 OneDrive 帳戶。請參閱前一節中存取及移轉 .wbx 檔案的步驟。
- 將白板複本儲存為 .png 檔案。

##### <a name="export"></a>匯出

如果您已取得白板的複本，即可將它匯出。 

1. 在 Surface Hub 上啟動 Whiteboard。
2. 點選 [共用] 按鈕，然後選取 [匯出複本]。您可以將白板匯出為 OneNote (.one) 檔案或影像 (.png) 檔案。

##### <a name="delete"></a>刪除

您可以授與自己存取使用者之商務用 OneDrive 帳戶的權限，然後刪除白板。

1. 授與您自己存取資料主體之商務用 OneDrive 帳戶的權限。請參閱[存取及備份先前使用者的資料](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)中的＜存取離職員工的商務用 OneDrive 文件＞一節。
2. 移至 [Whiteboard 應用程式資料] 資料夾，然後刪除此資料夾的內容。

#### <a name="whiteboard-for-pc-surface-hub-and-other-platforms"></a>適用於電腦、Surface Hub 及其他平台的 Whiteboard

如果系統管理員在新 Whiteboard 應用程式中收到對於資料的 DSR 要求，他們可以使用 Whiteboard PowerShell 將自己 (或其他使用者) 新增為使用者白板的擁有者。這可讓系統管理員執行動作，包括存取、匯出及刪除白板。使用 **Set-WhiteboardOwner** Cmdlet，將您自己或其他使用者新增為白板的擁有者，或使用 **Invoke-TransferAllWhiteboards** Cmdlet 將特定使用者的所有白板擁有權移轉給新的擁有者。如需有關使用這些 Cmdlet 及安裝 Whiteboard PowerShell 模組的相關資訊，請參閱 Microsoft Whiteboard Cmdlet 參考。在您或其他人員具有白板的擁有權之後，請參閱 [Microsoft Whiteboard Cmdlet 參考](https://docs.microsoft.com/powershell/module/whiteboard/?view=whiteboard-ps) (英文)。

在您或其他人員具有白板的擁有權之後，如需存取、匯出及刪除白板的詳細指引，請參閱 [Microsoft 白板說明](https://go.microsoft.com/fwlink/?linkid=872780)。

### <a name="yammer"></a>Yammer

下列各節說明如何使用 Microsoft Yammer 中的應用程式內功能，來尋找、存取、匯出及刪除個人資料。

#### <a name="discover"></a>探索

從 Yammer 系統管理中心，Yammer 驗證管理員 (全域系統管理員或在 Yammer 中設定的驗證管理員) 可以匯出與特定使用者相關的資料。 匯出包含使用者所張貼及修改的訊息和檔案，以及使用者所建立的主題和群組的相關資訊。 執行使用者特定資料匯出時，系統管理員也會收到收件匣訊息，其中附有使用者的帳戶活動資料；若系統管理員有意願，可將此資枓提供給使用者。 如需詳細指示，請參閱 [Yammer Enterprise：隱私權](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf)。

使用者特定匯出適用於單一網路；因此若使用者位於外部 Yammer 網路，則系統管理員必須針對該外部網路，以及針對家用網路匯出資料。

若要存取資料匯出中未包含的資料，可以針對使用者設定檔、設定、群組成員資格、加上書籤的訊息、追蹤的使用者以及追蹤的主題，取得螢幕擷取畫面。 使用者或系統管理員可以收集這些資訊。 如需詳細資訊，請參閱 [Yammer Enterprise：隱私權](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf)。

#### <a name="access"></a>Access

您可以檢視所匯出檔案中的資料，包括訊息的全文和檔案的內容。您也可以按一下所匯出檔案中的連結，直接移至 Yammer 中張貼的訊息和檔案，以及移至群組、使用者建立的主題、使用者喜歡的訊息、使用者為 @mentioned 的訊息、使用者已投票的民意調查和使用者已新增的連結。

按使用者的資料匯出不包括：

- 使用者的設定檔：
    - 如果使用者具有 Yammer 身分識別，使用者可以完全控制其設定檔。如需怎樣檢視和修改設定檔的相關資訊，請參閱[變更我的 Yammer 設定檔和設定](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851)。
    
    - 如果使用者具有 Office 365 身分識別，系統會自動從 Office 365 帶入 Yammer 使用者設定檔；這會從 Azure Active Directory (AAD) 取得設定檔資訊。Yammer 使用者可以暫時變更自己在 Yammer 的設定檔；但在 AAD 中發生變更時，會覆寫前者，因此您必須檢視並變更 AAD 中的目錄資料。請參閱[從 Office 365 跨其生命週期管理 Yammer 使用者](https://support.office.com/article/Manage-Yammer-users-across-their-life-cycle-from-Office-365-6c4c8fff-6444-404a-bffc-f9da0bcc3039)和[新增或變更 Azure Active Directory 中使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal)。

-   使用者的設定：

- 使用者可以檢視及變更自己的設定。如需如何檢視和修改使用者設定的相關資訊，請參閱[變更我的 Yammer 設定檔和設定](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851)。系統管理員可以檢視此資訊，並取得螢幕擷取畫面，但無法加以變更。請移至 [Yammer 設定] \> [人員]****，然後按一下使用者的名稱。<br/>
    - 使用者的群組成員資格、加上書籤的訊息、追蹤的使用者，以及追蹤的主題。
    
    - 使用者可以檢視此資訊。如需做法的相關資訊，請參閱[在 Yammer 保持井然有序的提示](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380)。系統管理員可以檢視此資訊，並取得螢幕擷取畫面，但無法加以變更。請移至 [Yammer 設定] \> [人員]****，然後按一下使用者的名稱。

#### <a name="export"></a>匯出

如需怎樣匯出資料的指示，請參閱[管理 Yammer Enterprise 中的 GDPR 資料主體要求](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf)。您必須針對使用者為其成員的每個 Yammer 網路，執行按使用者匯出。

Yammer 具有資料保留設定；當使用者刪除郵件或檔案時，這些設定可以虛刪除或實刪除資料。 若設定為「虛刪除」，則使用者已刪除的資料將繼續儲存。 如果 Yammer 資料保留設定設為「實刪除」，則已刪除的資訊便不會再儲存在 Yammer 中。

#### <a name="delete"></a>刪除

如果驗證管理員收到 DSR，Yammer 可讓驗證管理員透過 Yammer 系統管理中心，執行符合 GDPR 規範的刪除。此選項稱為 [清除使用者]，會將使用者暫停 14 天，然後移除其所有個人資料，但檔案和訊息除外。如果使用者是來賓使用者，則必須針對來賓使用者是其成員的每個外部網路執行此動作。

>[!NOTE]
>如果系統管理員想要在 14 天的時間範圍內移除使用者的檔案和訊息，則他們必須執行使用者層級匯出，來識別檔案和訊息，然後決定要透過產品內刪除，或使用 PowerShell 指令碼刪除哪些檔案和訊息。在 14 天的時間範圍後，系統管理員就無法再讓使用者與其檔案或訊息產生關聯。

使用 [清除使用者] 選項來刪除使用者時，系統會將通知傳送至所有網路管理員和驗證管理員的 Yammer 收件匣。[清除使用者] 選項會清除使用者的 Yammer 設定檔案，但不會刪除其 Office 365 或 Azure Active Directory 設定檔。

如需移除使用者的詳細步驟，請參閱[管理 Yammer Enterprise 中的 GDPR 資料主體要求](https://support.office.com/article/enterprise-privacy-yammer-eae49f12-4661-4ba5-aa72-01248f0709bf)。

## <a name="responding-to-dsr-rectification-requests"></a>回應 DSR 修正要求

如果資料主體要求您修正存在於儲存在 Office 365 中貴組織資料內的個人資料，則您和貴組織必須判斷接受要求是否適當。 如果您選擇接受要求，修正資料可能包含採取下列動作，例如：從文件或其他類型的項目中，編輯、刪減或移除個人資料。 最方便的方式是要求資料/文件擁有者，使用適當的 Office 365 應用程式來進行所要求的變更。 替代方法為讓貴組織中的 IT 系統管理員進行變更。 這可能需要 IT 系統管理員 (或貴組織中具有適當權限的其他人員，例如 SharePoint Online 網站集合管理員) 將存取文件或文件所在內容位置的必要權限，指派給自己或處理 DSR 的其他人，以便直接對文件進行變更。

### <a name="requesting-that-the-data-owner-to-make-the-approved-change"></a>要求資料擁有者進行經核准的變更

修正個人資料最直接的方式，就是要求資料擁有者進行變更。在找出作為 DSR 主體的資料之後，您可以提供下列資訊，讓資料擁有者能進行變更。

- 需要變更之項目的位置和檔案名稱 (適用於文件和其他檔案)； 步驟 1 中所描述的[探索程序](#using-content-search-to-find-personal-data)內，包含了如何找出上述資料。
- 資料擁有者應該進行的經核准變更

建議您考慮實施確認程序，讓您或參與 DSR 調查的其他人確認是否已進行所要求的變更。

### <a name="gaining-access-to-a-sharepoint-online-site-or-onedrive-for-business-account-to-make-changes"></a>存取 SharePoint Online 網站或商務用 OneDrive 帳戶進行變更

若無法讓資料擁有者實作資料主體的修正要求，則貴組織中的 IT 系統管理員或 SharePoint Online 系統管理員可以存取內容位置，並進行所需的變更。或者，系統管理員也可將必要的權限指派給您或其他資料隱私權主管。

#### <a name="sharepoint-online"></a>SharePoint Online

若要指派 Sharepoint 網站的系統管理員或擁有者權限，以便您或其他人可以存取及編輯該文件，請參閱

- [管理網站集合的系統管理員](https://support.office.com/article/Manage-administrators-for-a-site-collection-9A7E46F9-3FC4-4297-955A-82CB292A5BE0)

- [編輯和管理 SharePoint 清單或文件庫的權限](https://support.office.com/article/Edit-and-manage-permissions-for-a-SharePoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)

#### <a name="onedrive-for-business"></a>商務用 OneDrive

全域系統管理員可以存取使用者的商務用 OneDrive 帳戶。

1. 使用全域系統管理員認證登入 Office 365。
2. 移至系統管理中心。
3. 移至 [作用中使用者]****，然後選取使用者。
4. 展開詳細資料窗格中的 [商務用 OneDrive 設定]****，然後按一下 [存取檔案]****。
5. 按一下 URL 來移至使用者的商務用 OneDrive 帳戶。

### <a name="gaining-access-to-an-exchange-online-mailbox-to-make-changes-to-data"></a>存取 Exchange Online 信箱，對資料進行變更

全域系統管理員可將開啟和編輯 (或刪除) 其他使用者信箱中的項目 (就好像自己是信箱擁有者一樣) 所需的權利指派給自己。全域系統管理員也可以將這些權限指派給另一位使用者。具體來說，全域系統管理員需要新增**讀取及管理**權限，即 Exchange Online 中的完整存取權利。如需詳細資料，請參閱：

- [將信箱權限授與 Office 365 中的其他使用者](https://support.office.com/article/Give-mailbox-permissions-to-another-user-in-Office-365-Admin-Help-1DBCF12F-A9DE-4D1D-B0B3-A227F8A736D8)
- [存取另一個人員的信箱](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081)

如果使用者信箱置於法務保存措施，或已指派給保留原則，則會保留信箱的所有版本，直到保留期間到期，或從信箱中刪除了保留。 這表示，如果變更信箱項目以回應 DSR 修正要求，則會保留原始項目的複本 (在進行變更之前)，並儲存在使用者信箱的 [可復原的項目] 資料夾中的隱藏資料夾。

### <a name="making-changes-to-content-in-onedrive-for-business-and-sharepoint-online"></a>對商務用 OneDrive 和 SharePoint Online 中的內容進行變更

系統管理員或資料擁有者可對 SharePoint Online 文件、清單和頁面進行變更。在對 SharePoint 內容進行變更時，請記住下列事項：

- 更新文件將儲存文件的新版本，其中將包含修訂。 較舊版本的文件將不會更新。 這表示，作為 DSR 修正要求主體的資料，可能會持續保存在較舊版本的主題中。 您可以刪除較舊版本的主題，然後從 Office 365 中永久移除。 請參閱本指南中的[刪除 SharePoint Online 和商務用 OneDrive 中的文件](#deleting-documents-in-sharepoint-online-and-onedrive-for-business)一節。
- 若要以從檔案中移除資料主體之所有追蹤的方式來刪減 SharePoint 檔案，包括所有版本的檔案和資料主體所執行的所有記錄活動，您必須執行下列步驟：

    1. 將檔案的複本下載到本機電腦。
    2. 請從 SharePoint Online 中先刪除檔案，然後從第一階段和第二階段資源回收筒刪除，以便永久刪除檔案。請參閱本指南中的[刪除 SharePoint Online 和商務用 OneDrive 中的文件](#deleting-documents-in-sharepoint-online-and-onedrive-for-business)一節。
    3. 對本機電腦上的文件複本進行修訂。
    4. 將修訂後的檔案上傳至原始 SharePoint Online 位置。

- 可以編輯 SharePoint 清單中的資料。請參閱[新增、編輯或刪除清單項目](https://support.office.com/article/add-edit-or-delete-list-items-a4b31f53-f044-470e-9823-4526594bacde)。

IT 系統管理員也可以更正與文件相關聯的特定個人內容：

來自 SharePoint 使用者設定檔或 Office 365 的使用者資訊通常與商務用 OneDrive 和 SharePoint Online 文件相關聯，以代表該人員。例如，文件或清單項目的 [建立者] 或 [修改者] 欄位中的使用者名稱。有數種方式可修正此使用者資訊，視來源而定：

- 修正自己的內部部署 Active Directory 中的使用者內容。 對於會同步處理使用者內容 (例如來自內部部署 AD 的使用者顯示名稱、名字等) 的客戶，應該在內部部署 Active Directory 中修正這些內容。 適當對應的內容會流入 Office 365，再流入商務用 OneDrive 和 SharePoint Online。
- 修正系統管理中心的使用者內容。 在這裡對帳戶資訊所做的變更會自動反映在商務用 OneDrive 和 SharePoint Online 體驗中。 如需資訊，請參閱[新增或變更 Azure Active Directory 中使用者的設定檔資訊](https://go.microsoft.com/fwlink/?linkid=864809)。 對於從 Office 365 中所獲得的內容，無法對 SharePoint 端進行任何變更。
- 修正 SharePoint 系統管理中心的 SharePoint 使用者設定檔體驗中的使用者內容。在 SharePoint 系統管理中心的 [使用者設定檔] 索引標籤中，按一下 [管理使用者設定檔]****，並查看任何使用者的內容。然後，他們就可以選擇編輯使用者內容。
- 修正自訂來源中的使用者內容。自訂 SharePoint 設定檔內容可以透過 Microsoft Identity Manager (MIM) 或另一種方法，從自訂來源進行同步處理。

這並不會影響所有體驗，但可能會保留較舊的資訊。 例如，文件中以文字表示的使用者名稱。

### <a name="making-changes-to-content-in-power-bi"></a>對 Power BI 中的內容進行變更

Power BI 依賴用於其儀表板和報告的基礎來源資料，才能完整且精確，所以必須在基礎來源資料中更正不精確或不完整的來源資料。例如，如果您建立了連線至 Dynamics 365 for Sales 的 Power BI 報告，作為即時資料來源，則您必須在 Dynamics 365 for Sales 中對資料進行所有更正。

進行這些變更之後，您可以利用[排定的資料重新整理](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh)功能，來更新儲存在 Power BI 的資料集，以便修訂後的資料會反映在相依 Power BI 資產中。為了符合 GDPR 需求，您應該具有適當的原則，以確保您以適當的韻律重新整理您的資料。

### <a name="making-changes-to-content-in-yammer"></a>對 Yammer 中的內容進行變更

針對訊息，使用者可以編輯特定訊息，來修正任何不精確之處。他們可以從 Yammer 驗證管理員要求其所有訊息的清單，然後按一下檔案中的連結，檢閱每一個訊息。

針對檔案，使用者可以編輯特定檔案，來修正任何不精確之處。他們可以從 Yammer 驗證管理員要求他們所張貼之所有檔案的清單，然後存取 Yammer 中的檔案。您可以依編號搜尋檔案，來檢視匯出至 [檔案] 資料夾的檔案。例如，對於匯出中名為 12345678.ppx 的檔案，使用 Yammer 中的 [搜尋] 方塊搜尋 1235678.ppx。或者，移至 <strong> https://www.yammer.com/\<network\_name\>/\#/files/\<file\_number\> </strong>；例如，<strong> https://www.yammer.com/contosomkt.onmicrosoft.com/\#/files/12345678 </strong>。

對於使用者可以透過其設定檔和設定存取的資料，使用者可以進行任何需要的變更。

- 使用者的設定檔：

    - 如果使用者具有 Yammer 身分識別，使用者可以完全控制其設定檔。如需怎樣檢視和修改設定檔的相關資訊，請參閱[變更我的 Yammer 設定檔和設定](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851)。
    - 如果使用者具有 Office 365 身分識別，系統會自動從 Office 365 帶入 Yammer 使用者設定檔；這會從 Azure Active Directory (AAD) 取得設定檔資訊。 Yammer 使用者可以暫時變更自己在 Yammer 的設定檔；但在 AAD 中發生變更時，會覆寫前者，因此最好在 AAD 中檢視和變更目錄資料。 使用者需要要求系統管理員更新其 AAD。 請參閱[從 Office 365 跨其生命週期管理 Yammer 使用者](https://support.office.com/article/Manage-Yammer-users-across-their-life-cycle-from-Office-365-6c4c8fff-6444-404a-bffc-f9da0bcc3039)和[新增或變更 Azure Active Directory 中使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal)。

- 使用者的設定：

    - 使用者可以變更自己的設定。如需怎樣檢視和修改使用者設定的相關資訊，請參閱[變更我的 Yammer 設定檔和設定](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851)。
    - 使用者的群組成員資格、加上書籤的訊息、追蹤的使用者，以及追蹤的主題。使用者可以變更此資訊。請參閱[在 Yammer 中保持井然有序的提示](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380)。

## <a name="responding-to-dsr-restriction-requests"></a>回應 DSR 限制要求

以下是限制處理 Office 365 中資料的方式：

- 移除 Office 365 應用程式授權，以防止使用者透過應用程式存取資料
- 防止使用者存取其商務用 OneDrive 帳戶
- 關閉 Office 365 服務，不處理資料
- 暫時移除 SharePoint Online 和商務用 OneDrive 中的資料，並保留在內部部署
- 暫時限制對 SharePoint Online 網站的所有存取
- 防止使用者登入 Office 365

如果貴組織稍後決定限制不再適用，您可以反轉採取限制的步驟來結束限制；例如，重新指派授權、再次開啟服務，或允許使用者登入 Office 365。

### <a name="removing-the-license-for-an-office-365-application"></a>移除 Office 365 應用程式的授權

如同先前所述，根據預設，貴組織商務用 Microsoft 365 訂閱中包含的所有 Office 365 應用程式的授權已指派給所有使用者。 必要時，若要限制存取受制於 DSR 的資料，IT 系統管理員可以使用 Office 365 系統管理員入口網站，暫時關閉使用者對某應用程式的授權。 如果使用者隨後嘗試使用該應用程式，則他們將會收到未授權的產品通知或他們不會再有權存取的訊息。 如需詳細資料，請參閱[從商務用 Office 365 中的使用者移除授權](https://support.office.com/article/Remove-licenses-from-users-in-Office-365-for-business-9B497C85-D0A4-4735-80FA-D3565BC05BD1)。

**注意：**

- 若要限制使用者存取 Yammer，首先您必須[強制執行 Yammer 使用者的 Office 365 身分識別](https://support.office.com/article/Enforce-office-365-identity-for-Yammer-users-008f940b-6bec-47fc-bcc6-9c6133467562)，然後移除使用者的 Yammer 授權。

- 對於利用 Power BI Embedded 的案例，您可以限制存取內嵌內容的獨立軟體廠商 (ISV) 應用程式。

### <a name="preventing-users-from-accessing-their-onedrive-for-business-account"></a>防止使用者存取其商務用 OneDrive 帳戶

移除使用者的 SharePoint Online 授權，並無法防止使用者存取其商務用 OneDrive 帳戶 (若已存在的話)。 您必須移除使用者對其商務用 OneDrive 帳戶的權限。 做法為以其商務用 OneDrive 帳戶的網站集合擁有者身分移除使用者。 具體來說，您必須從其使用者設定檔中的主要網站集合系統管理員網站集合系統管理員「主要網站集合管理員」和「網站集合管理員」群組中移除使用者。 請參閱[管理 SharePoint 管理中心的使用者設定檔](https://docs.microsoft.com/sharepoint/manage-user-profiles)中的＜新增和移除商務用 OneDrive 帳戶上的系統管理員＞一節。

### <a name="turning-off-an-office-365-service"></a>關閉 Office 365 服務

解決 DSR 要求來限制處理資料的另一種方法，就是是關閉 Office 365 服務。 這會影響整個組織中的所有使用者，並防止每個人使用服務，或存取服務中的資料。

關閉服務最方便的方式是使用 Office 365 PowerShell，並從組織中的所有使用者移除對應的使用者授權。這會實際上限制任何人存取該服務中的資料。如需詳細指示，請參閱[使用 Office 365 PowerShell 停用服務的存取](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)，並遵循程序從單一授權方案停用使用者的 Office 365 服務。

>[!NOTE]
>針對 Yammer，除了從使用者帳戶中移除 Yammer 授權之外，您也必須將使用者使用 Yammer 認證登入 Yammer 的能力停用 (透過在登入時，強制使用 Office 365 認證)。如需詳細指示，請參閱[關閉 Microsoft 365 使用者的 Yammer 存取](https://support.office.com/article/Turn-off-Yammer-access-for-Office-365-users-1f79bfad-f713-4143-aa5d-5584985ce53a)。

### <a name="temporarily-removing-data-from-sharepoint-online-or-onedrive-for-business-sites"></a>暫時從 SharePoint Online 或商務用 OneDrive 網站中移除資料

限制處理個人資料的另一種方法，就是暫時從 Office 365 DSR 中移除它，以回應 DSR。當貴組織決定限制不再適用時，您可以將資料匯回至 Office 365。

因為大部分 Office 文件位於 SharePoint Online 或商務用 OneDrive 網站，以下是從網站中移除文件，然後重新匯入的高層級程序。

1. 取得作為限制要求主體的文件複本。您可能必須要求存取網站，或要求全域管理員或網站集合系統管理員提供您文件的複本。
2. 將文件儲存在內部部署位置 (例如檔案伺服器或檔案共用) 中，或 Microsoft 雲端中 Office 365 租用戶以外的另一個位置中。
3. 從 Office 365 中永久刪除 (清除) 原始文件。這是 3 步驟的程序：

    a. 刪除文件的原始複本。當您從網站中刪除文件時，此文件會傳送至資源回收筒 (又稱為「第一階段資源回收筒」**)。

    b. 移至網站資源回收筒，並刪除該文件複本。當您從網站資源回收筒中刪除文件時，此文件會傳送至網站集合資源回收筒 (又稱為「第二階段資源回收筒」**)。請參閱[從 SharePoint 文件庫中刪除檔案、資料夾或連結](https://support.office.com/article/Delete-a-file-folder-or-link-from-a-SharePoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52)。

    c. 移至網站集合資源回收筒，然後刪除該文件複本，這會從 Office 365 中永久將其移除。請參閱[從網站集合資源回收筒中刪除項目](https://support.office.com/article/Delete-items-from-the-site-collection-Recycle-Bin-dd5c00c2-aef6-4458-9d04-80b185077653)。

4. 當限制不再適用時，已儲存在內部部署的文件複本可以重新上傳至 Office 365 中的網站。

>[!IMPORTANT]
>如果文件位於處於保留狀態的網站 (具有 Office 365 的其中一個保留或法務保存措施功能)，則先前程序無法運作。在 DSR 限制要求的優先權高於法務保存措施的情況下，您必須先從網站中移除保留，然後才能永久刪除文件。此外，這也會永久移除已刪除文件的文件歷程記錄。

### <a name="temporarily-restricting-access-to-sharepoint-online-sites"></a>暫時限制存取 SharePoint Online 網站

SharePoint Online 系統管理員可以鎖定網站集合來暫時防止所有使用者存取 SharePoint Online 網站集合 (透過使用 SharePoint Online PowerShell 中的 **Set-sposite LockState** 命令)。 這會防止使用者存取網站集合，以及位於該網站的任何內容或資料。 如果您隨後判斷使用者應該能夠存取網站，系統管理員可以解除鎖定網站。 如需執行此 PowerShell Cmdlet 的相關資訊，請參閱 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite)。

### <a name="preventing-a-user-from-signing-in-to-office-365"></a>防止使用者登入 Office 365

IT 系統管理員也可以防止使用者登入 Office 365，這會防止使用者存取任何 Office 365 線上服務，或處理儲存在 Office 365 中的任何資料。請參閱[封鎖離職員工對 Office 365 資料的存取](https://support.office.com/article/Remove-a-former-employee-from-Office-365-44d96212-4d90-4027-9aa9-a95eddb367d1)。

## <a name="part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365"></a>第 2 部分：按照 Office 365 產生的見解來回應 DSR

Microsoft Office 365 服務套件包含線上服務，可對已選擇使用服務的使用者和組織提供見解。

- Delve 和 MyAnalytics 可提供見解給個別使用者
- 工作場所分析可提供見解給組織。

下列各節描述這些服務：

### <a name="delve"></a>Delve

在 Delve 中，使用者可以管理其 Office 365 設定檔，並探索人員以及與他們相關的文件。 使用者只能看到他們有權存取的文件。 如需一系列有關 Delve 的有用文件，請參閱 [Microsoft Delve](https://support.office.com/article/What-is-Office-Delve-1315665a-c6af-4409-a28d-49f8916878ca)。

#### <a name="access-and-export"></a>存取及匯出

系統管理員無法存取或匯出使用者的 Delve 資料。這表示，使用者必須自行存取和匯出 Delve 資料。這些資料類型大多可讓使用者直接從 Delve 存取和匯出，但某些資料類型只能透過其他服務來使用。

##### <a name="data-available-in-the-delve-user-interface"></a>可在 Delve 使用者介面中使用的資料

- **設定檔資料：** 這是來自 Azure Active Directory 中貴組織全域通訊清單的設定檔資訊，以及使用者選擇新增有關本身的選擇性資訊。 若要存取或匯出 Delve 中的設定檔資料，使用者可以按一下 [我]**** \> [更新設定檔]****。 他們可以從頁面直接複製內容，或
- **部落格資料：** 這是使用者發佈的部落格文章。 若要存取或匯出部落格資料，使用者可以按一下 [我]**** \> [所有文章]****。 他們可以從頁面直接複製內容，或取得螢幕擷取畫面。
- **最新人員資料：** 以下是組織中 Delve 已推斷在指定時間與使用者最相關的人員。 當使用者在 [按一下人員以查看他們正在處理的項目] 窗格中按一下 [我]**** \> [查看全部]**** 時，Delve 會顯示指定時間使用者的最相關人員。

##### <a name="data-available-through-an-export-link-in-delve"></a>可透過 Delve 中的匯出連結提供的資料

- **人員清單資料：** 這些是使用者已在 Delve 中檢視的人員。 [人員]**** 清單會顯示在首頁的左窗格中。 使用者可以匯出他們最近在 Delve 中檢視的人員清單。
- **我的最愛資料：** 這些是使用者已標示為我的最愛的討論區和文件。 [我的最愛]**** 頁面會顯示使用者已新增至我的最愛的討論區和文件。 使用者可以匯出其目前我的最愛討論區和文件的清單。
- **功能設定資料：** 這些是使用者使用 Delve 所產生的 Delve 組態或動作。 使用者可以匯出這些設定的完整清單。

若要存取或匯出上述資料，使用者可以按一下 Delve 右上角的齒輪圖示，然後按一下 [功能設定]**** > [匯出資料]****。資訊是以 JSON 格式匯出。

##### <a name="data-thats-available-through-other-services"></a>可透過其他服務提供的資料

- **熱門文件資料：** 這些是可能與使用者相關的文件和電子郵件附件。 Delve 會根據使用者的活動，以及他們在 Office 365 中使用的人員，動態組織這些文件和電子郵件訊息。 當使用者開啟 Delve，或按下 [首頁]**** 時，Delve 會顯示特定時間使用者的最相關文件或附件。 若要存取或匯出實際的文件和附件，使用者可以移至已透過其提供文件或附件的 Office 365 服務 (例如 Office.com、SharePoint Online、商務用 OneDrive，或 Exchange Online)。
- **最新的文件和電子郵件附件資料：** 這是使用者已修改的最新文件和電子郵件附件。 當使用者在 [取回您的最新文件和電子郵件附件] 窗格中按一下 [我]**** \> [查看全部]**** 時，Delve 會顯示使用者已在特定時間修改的最新文件和電子郵件附件。 若要存取或匯出實際的文件和附件，使用者可以移至已透過其提供文件或附件的 Office 365 服務，例如 Office.com、SharePoint Online、商務用 OneDrive，或 Exchange Online。
- **來自您周圍人員資料的文件：** 以下是 Delve 已推斷在特定時間與使用者最相關的文件。 當使用者在 [探索來自您周遭人員的文件] 窗格中按一下 [我]**** \> [查看全部]**** 時，Delve 會顯示特定時間使用者的最相關文件。 若要存取或匯出實際的文件，使用者可以移至已透過其提供文件或附件的 Office 365 服務，例如 Office.com、SharePoint Online、商務用 OneDrive 或 Exchange Online。

#### <a name="rectify"></a>修正

使用者可以修改 Delve 中的下列資訊：

- **設定檔資訊：** 使用者可以按一下 **[我]** \>**[更新設定檔]**，來更新其資訊。 根據貴組織的全域通訊清單中的設定，使用者可能無法修改所有設定檔資訊，例如其名稱或職稱。
- **功能設定：** 使用者可以按一下 Delve 右上角的齒輪圖示，然後按一下 **[功能設定]** \>來變更所需的設定。

#### <a name="restrict"></a>限制

若要針對貴組織限制 Delve 中的處理，您可以關閉 Office Graph。如需深入了解，請參閱[這裡](https://support.office.com/article/office-delve-for-office-365-admins-54f87a42-15a4-44b4-9df0-d36287d9531b#bkmk_delveonoff)。

#### <a name="delete"></a>刪除

使用者可以刪除 Delve 中的下列資訊：

- **設定檔資訊：** 若要刪除設定檔資訊，使用者可以按一下 **[我]** \> **[更新設定檔]**，來刪除自由格式文字。 根據貴組織的全域通訊清單中的設定，使用者可能無法刪除其所有設定檔資訊，例如其名稱或工作職稱。
- **文件和電子郵件附件：** 若要刪除文件或附件，使用者必須移至儲存文件或附件的服務 (例如 SharePoint Online、商務用 OneDrive，或 Exchange Online)，並刪除那裡的文件。

### <a name="myanalytics"></a>MyAnalytics

MyAnalytics 可提供統計資料給使用者，以協助他們了解工作時間分配。若要協助您的使用者深入了解在其個人儀表板中呈現給他們的資料，以及資料的計算方式，請將您的使用者導向至 [MyAnalytics 個人儀表板](https://docs.microsoft.com/workplace-analytics/myanalytics/use/dashboard-2)說明主題。

#### <a name="access-and-export"></a>存取及匯出

如果您的組織使用 MyAnalytics，則 Microsoft 會為所有使用者產生見解。 MyAnalytics 的所有見解都衍生自使用者信箱中的電子郵件和會議標題。 Microsoft 讓您能夠在安全性與合規性中心使用 DSR 案例工具，匯出 MyAnalytics 用來產生這些見解的資料。如需詳細指示，請參閱[從 MyAnalytics 和 Office 漫遊服務匯出資料](https://delve.office.com)。 如果他們想要擁有其資訊的永久複本，他們可以製作 MyAnalytics 見解的螢幕擷取畫面。

#### <a name="rectify"></a>修正

MyAnalytics 所產生的所有見解都是衍生自使用者的郵件和行事曆項目。因此，除了來源電子郵件或行事曆項目外，沒有要修正的項目。

#### <a name="restrict"></a>限制

若要限制特定使用者的處理，您可以從 MyAnalytics 排除它們。若要查看如何進行，請參閱[設定 MyAnalytics 使用者設定](https://docs.microsoft.com/workplace-analytics/myanalytics/setup/configure-myanalytics)。

#### <a name="delete"></a>刪除

從 Active Directory 中「實刪除」使用者帳戶時，會清除所有信箱內容，包括 MyAnalytics 資料。如需詳細資訊，請參閱本指南的[刪除使用者](#deleting-a-user)一節。

### <a name="workplace-analytics"></a>工作場所分析

「工作場所分析」可讓組織利用其自己的商務資料來擴增 Office 365 資料，以深入了解組織生產力、共同作業模式和員工參與度。[本文](https://docs.microsoft.com/workplace-analytics/index-orig)說明了貴組織對工作場所分析處理的資料所具有的控制權，以及誰有權存取該資料。

為了協助在工作場所分析中使用 DSR： 

1. 請判斷貴組織是否使用「工作場所分析」。如需詳細資訊，請參閱[將授權指派給使用者](../admin/manage/assign-licenses-to-users.md)。如果您的組織並未使用「工作場所分析」，則不需採取進一步動作。

2. 如果貴組織使用「工作場所分析」，接著請查看貴組織中誰被指派給工作場所分析系統管理員的角色。 您也應該判斷資料主體的信箱是否有「工作場所分析」的授權。 如有需要，讓工作場所分析系統管理員在處理下列 DSR 要求時連絡 Microsoft 支援服務： 

#### <a name="access-and-export"></a>存取及匯出

您所建立的「工作場所分析」報告中的見解不一定包含貴組織已對「工作場所分析」授權之使用者的個人資料，視貴組織用來補充 Office 365 資料的資訊而定。 您的工作場所分析系統管理員必須檢閱這些報告，才能判斷它們是否包含使用者的個人資料。 如果報告的確包含使用者的個人資料，則您必須決定是否要提供該報告的複本給使用者。 「工作場所分析」可讓您匯出報告。 

#### <a name="rectify"></a>修正

如上所述，「工作場所分析」會使用 Office 365 資料，結合您提供的組織資料，來產生您有興趣的報告。 無法修正 Office 365 資料；這取決於使用者的電子郵件和行事曆活動。 不過，您可以修正已上傳至「工作場所分析」以便產生報告的組織資料。 若要這麼做，您必須修正來源資料、上傳，然後重新執行報告，來產生新的「工作場所分析」報告。

#### <a name="restrict"></a>限制

若要限制特定使用者的處理，您可以移除他們的「工作場所分析」授權。

#### <a name="delete"></a>刪除

如果想要從一或多份「工作場所分析」報告中移除資料主體，您可以刪除該報告。您需負責從您用來產生報告的任何組織資料中刪除使用者，並且重新上傳資料。從 Azure Active Directory 中「實刪除」使用者帳戶時，就會移除有關使用者的所有資料。 

若要移除資料主體的個人資料，全域系統管理員可以執行下列步驟： 

1. 移除資料主體的工作場所分析授權。
2. 刪除資料主體的 Azure Active Directory (AAD) 項目。(如需詳細資訊，請參閱[刪除使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user)。)
3. 連絡支援人員並請支援人員為資料主體權限 (DSR) 使用者刪除要求開啟票證。在此票證中，使用資料主體的使用者主要名稱 (UPN) 來識別資料主體。
4. 從公司的人力資源系統匯出人力資源資料複本 (請參閱[匯出資料](https://docs.microsoft.com/workplace-analytics/setup/prepare-organizational-data))，從該人力資源資料檔案中移除資料主體的資訊，然後將已編輯的 .csv 格式人力資源資料檔案上傳到工作場所分析 (請參閱[上傳組織資料](https://docs.microsoft.com/workplace-analytics/setup/upload-organizational-data))。

## <a name="part-3-responding-to-dsrs-for-system-generated-logs"></a>第 3 部分：回應系統所產生記錄的 DSR

Microsoft 也讓您能夠存取、匯出及刪除系統所產生的記錄，根據 GDPR「個人資料」的廣泛定義，這些記錄可能會視為個人資料。系統所產生的記錄中，根據 GDPR可能會視為個人資料的範例包括：

- 產品和服務使用情況資料 (例如使用者活動記錄)
- 使用者搜尋要求和查詢資料
- 作為系統功能與使用者或其他系統互動的產品和服務所產生的資料

系統不支援在系統產生的記錄中限制或修正資料的能力。 系統所產生的記錄構成了 Microsoft 雲端中所進行的實際動作和診斷資料，對這類資料的修改會危害動作的歷程記錄，並增加詐騙和安全性風險。

### <a name="accessing-and-exporting-system-generated-logs"></a>存取和匯出系統所產生的記錄

「資料可攜性權利」允許資料主體以電子格式 (即「結構化、常用、機器可讀取格式」)，要求其個人資料的複本，並可傳輸給其他資料控制者。 Azure 可支援這點；我們讓貴組織能以原生 JSON 格式，將資料匯出到您指定的 Azure 儲存體容器。

>[!IMPORTANT]
>您必須是租用戶系統管理員，才能從租用戶中匯出使用者資料。

#### <a name="azure-active-directory"></a>Azure Active Directory

至於客戶資料，Microsoft 同時提供入口網站與產品內體驗，讓企業客戶的租用戶系統管理員能夠管理使用者識別資訊的匯出要求。

#### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

### <a name="deleting-system-generated-logs"></a>刪除系統產生的記錄

若要透過存取要求來刪除系統產生的記錄，您必須將使用者從該服務中移除，並永久刪除其 Azure Active Directory 帳戶。如需永久刪除使用者的相關指示，請參閱本指南中[刪除使用者](#deleting-a-user)一節。請務必注意，一旦開始永久刪除使用者帳戶即無法復原。

永久刪除使用者帳戶會在 30 天內將使用者資料，從幾乎所有 Office 365 服務產生的系統記錄中移除 (可能危及服務安全性或穩定性的資料除外)。 有一個例外，就是 Exchange Online，其永久刪除使用者帳戶所需的時間超過 30 天。 有鑑於 Exchange Online 內容的重要本質，並防止資料意外流失， 此系統已經過設計，在永久刪除了使用者帳戶之後，故意將處於保留狀態的資料最多保留 60 天。 若要在 30 天時間範圍內永久刪除使用者的 Exchange Online 資料，請永久刪除 Azure Active Directory 中的使用者帳戶，然後連絡 [Microsoft 支援](https://support.microsoft.com/)，並要求在排定的刪除程序外手動移除使用者的 Exchange Online 資料。 如需詳細資訊，請參閱本指南先前所述的[移除 Exchange Online 資料](#removing-exchange-online-data)。

刪除使用者帳戶不會移除系統為 Yammer 和 Kaizala 所產生的記錄。若要從這些應用程式中移除資料，請參閱以下其中一項：

- Yammer - [管理 Yammer Enterprise 中的 GDPR 資料主體要求](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- Kaizala - [在 Kaizala 中匯出或刪除使用者的組織資料](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

#### <a name="national-clouds"></a>國家雲

全域 IT 系統管理員必須執行下列動作來刪除下列國家雲中系統所產生的記錄：

- Office 365 Germany - 永久刪除使用者帳戶時，系統產生的記錄也會一併刪除。 
- Office 365 US Government - 透過 [Office 365 系統管理入口網站](https://portal.office365.us)將要求提交給 Microsoft 支援服務。
- 由 21Vianet (中國) 運作的 Office 365 - 透過位於此 [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage) 的 Office 365 系統管理入口網站，將要求提交給 Microsoft 支援服務。移至 [商務]****，然後選取 [訂用帳戶]****  ->  [隱私權]****  ->  [GDPR]****，然後輸入必要的資訊。

## <a name="part-4-additional-resources-to-assist-you-with-dsrs"></a>第 4 部分：其他協助您使用 DSR 的資源

### <a name="dsr-guides-for-other-microsoft-enterprise-services"></a>Microsoft 企業服務的 DSR 指引

本指南專注於當使用 Office 365 產品、服務及系統管理工具時，如何尋找並處理個人資料以回應 DSR 的主題。 請移至 [Microsoft 服務信任入口網站](https://servicetrust.microsoft.com/)，來存取其他 Microsoft 企業服務的類似指引。

### <a name="microsoft-support"></a>Microsoft 支援

「支援資料」是您和您的使用者在貴組織或您的使用者與 Microsoft 接洽，以接收與 Office 365 或其他 Microsoft 產品和服務相關的產品支援 (例如對非預期的產品行為進行疑難排解) 時，提供給 Microsoft 的資料。如需詳細資訊，請參閱 [GDPR 的 Microsoft 支援與專業服務資料主體要求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-prof-services)。

### <a name="product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller"></a>使用組織識別碼驗證的產品和服務，Microsoft 是其資料控制者

本指南的第 1 至 3 部分涵蓋 Microsoft 是貴組織之資料處理者的產品和服務，因此 DSR 功能可供您的租用戶系統管理員使用。 有各種不同情況，其中貴組織的使用者可能使用其公司或學校帳戶 (也稱為「Azure Active Directory 識別碼」或「AAD」) 來登入Microsoft 是資料控制者的 Microsoft 產品和服務。 對於所有這類產品和服務，您的使用者必須直接向 Microsoft 提出資料主體要求，而且 Microsoft 將會直接對使用者履行要求。 經由設計，涉及儲存使用者撰寫內容的產品和服務可讓使用者存取、匯出、修正和刪除其使用者撰寫的內容，這是產品既有產品功能的一部分。 可能適用此情況的情節如下：

- **選擇性連線的線上服務：** 企業用 Microsoft 365 應用程式會使特定選擇性連線的線上服務可供使用者使用。 服務和相關使用者控制項的清單會列在[這裡](https://support.office.com/article/microsoft-s-other-connected-services-92c234f1-dc91-4dc1-925d-6c90fc3816d8)。 您可以決定是否要允許使用者使用這些服務。 如需詳細資訊，請參閱[系統管理員如何在企業用 Microsoft 365 應用程式中管理控制器服務](https://docs.microsoft.com/DeployOffice/manage-controller-services-office-365-proplus)。 如果這些選擇性服務處理個人資料，Microsoft 是這些服務的資料控制者。
- **使用者意見反應：** 如果使用者選擇提供對 Microsoft 產品和服務提供意見反應，則 Microsoft 是這類意見反應的資料控制者，甚至其中包含個人資料。 Microsoft 將會對 Microsoft 所收集的意見反應履行任何資料主體要求 (包括由 Microsoft 子處理者所管理的意見反應)，但若 Microsoft 已指示使用者不要在意見反應收集過程中包含個人資料，則不在此限。 例外：如果 Microsoft 已指示使用者不要在意見反應收集過程中包含個人資料，則 Microsoft 將信賴該指示，並將假設未提供任何個人資料。 已利用第三方意見反應服務提供者建立個別帳戶的使用者必須直接向那些提供者履行其 DSR。
- **Windows 透過公司或學校帳戶來驗證** - 如果貴組織已購買 Windows 授權，而且您的使用者使用其公司或學校帳戶向組織提供的 Windows 進行驗證，Microsoft 會充當資料控制者。
- **使用者取得的產品或服務** - 如果您允許您的使用者以其個人身分取得使用 AAD 進行驗證的 Microsoft 產品或服務 (例如 Office 附加元件或可在 Microsoft Store 取得的應用程式)，Microsoft 可能是資料控制者。 對於任何這類 Microsoft 產品或服務，使用者必須直接連絡 Microsoft 來發出 DSR。

>[!IMPORTANT]
>如果您刪除透過 Azure Active Directory 啟用的使用者，則您的 (先前) 使用者將無法登入任何產品或服務，其先前倚靠公司或學校帳戶來使用它們。此外，Microsoft 將再也無法驗證與產品或服務之 DSR 要求有關的使用者，Microsoft 是資料控制者。如果您想要讓使用者可以對這類服務發出 DSR，請務必指示您的使用者在刪除使用者的 AAD 帳戶之前先這樣做。

### <a name="personal-accounts"></a>個人帳戶

如果您的使用者已使用 Microsoft 帳戶 (亦即個人帳戶)，從 Microsoft 取得供他們自己使用的產品和服務，而且 Microsoft 是資料控制者，則他們可能會使用 [Microsoft 隱私權儀表板](https://account.microsoft.com/account/privacy)來發出 DSR 要求。

### <a name="third-party-products"></a>協力廠商產品

如果貴組織或您的使用者以其個人身分從協力廠商取得產品和服務，並使用 Microsoft 公司或學校帳戶進行驗證，則任何資料主體要求都應該導向至適當的協力廠商。

## <a name="appendix-a-preparing-for-dsr-investigations"></a>附錄 A：準備 DSR 調查

若要準備讓貴組織使用 Office 365 服務進行 DSR 調查，請考慮下列建議：

- 使用安全性與合規性中心的 DSR 電子文件探索案例工具來管理 DSR 調查
- 設定合規性界限來限制內容搜尋的範圍
- 在 DSR 調查時使用稽核記錄搜尋工具

### <a name="use-the-dsr-case-tool-to-manage-dsr-investigations"></a>使用 DSR 案例工具來管理 DSR 調查

建議您使用 安全性與合規性中心的 DSR 案例工具，來管理 DSR 調查。使用 DSR 案例工具，您可以：

- 針對每一個 DSR 調查建立個別案例。

- 使用內建功能來搜尋與特定資料主體相關的所有內容。 當建立新的案例並開始搜尋時，會搜尋這些內容位置：

   - 您組織中的所有信箱 (包括與所有 Microsoft Teams 和 Microsoft 365 群組相關聯的信箱)
   - 貴組織中所有的 Sharepoint 網站和商務用 OneDrive 帳戶
   - 貴組織中所有的 Microsoft Teams 網站和 Microsoft 365 群組網站
   - Exchange Online 中的所有公用資料夾

- 修改預設搜尋查詢，然後重新執行搜尋來縮小搜尋結果。

- 藉由將人員新增為案例成員，來控制誰有權存取此案例；只有成員才能存取案例，而且在安全性與合規性中心內的 DSR 案例頁面上，他們只能在案例清單上看到自己的案例。 此外，您也可以將不同的權限指派給相同案例的不同成員。 例如，您可以允許某些成員只能檢視案例和內容搜尋的結果，而允許其他成員建立搜尋並匯出搜尋結果。

- 建立匯出工作來匯出搜尋結果，以回應 DSR 匯出要求。 您可以匯出內容搜尋所傳回的所有內容。 此外，也會匯出與資料主體相關的其他 Office 365 資料。

- 建立匯出工作來匯出搜尋結果，以回應 DSR 匯出要求。 您可以匯出內容搜尋所傳回的所有內容。 此外，您可以針對 Office 漫遊服務匯出系統產生的記錄。

- DSR 調查程序完成時，請刪除案例。 這會移除與案例相關聯的所有內容搜尋和匯出工作。

若要開始使用 DSR 案例，請參閱[使用安全性與合規性中心的 DSR 案例工具來管理 GDPR 資料主體要求](https://support.office.com/article/manage-dsr-cases-in-the-office-365-security-compliance-center-ce9eb942-3589-42cb-88fd-1576ecb09c5c)。

>[!IMPORTANT]
>電子文件探索管理員可以檢視和管理貴組織中所有的 DSR 案例。如需有關不同電子文件探索角色的詳細資訊，請參閱[將電子文件探索權限指派給潛在案例成員](https://docs.microsoft.com/Office365/SecurityCompliance/assign-ediscovery-permissions) 。

### <a name="set-up-compliance-boundaries-to-limit-the-scope-of-content-searches"></a>設定合規性界限來限制內容搜尋的範圍

您可以使用安全性與合規性中心的搜尋權限篩選功能，來實作合規性界限。合規性界限會在組織內建立邏輯搜尋界限，以控制/限制 IT 系統管理員或法務人員可以搜尋哪些內容位置 (例如 Exchange Online 信箱和 SharePoint Online 網站)。對於需要遵守地理界限的跨國組織、需要區隔不同機構的政府組織，以及隔離成業務單位或部門的企業組織，合規性界限會很有用。對於上述所有情況，合規性界限都可以用於 DSR 調查，以限制參與調查的人員可以搜尋的信箱和網站。

您可以搭配使用合規性界限與電子文件探索案例，將可在調查中搜尋的內容位置僅限制為機構或業務單位內的位置。

以下是如何針對 DSR 調查實作合規性界限 (與電子文件探索案例搭配) 的高階概觀。

1. 決定貴組織中要指定為合規性界限的機構。

2. 決定 Azure Active Directory 中哪個使用者物件屬性將用來定義合規性界限。例如，您也可以選擇 Country、CountryCode 或 Department 屬性，以便您在下一個步驟中建立的系統管理員角色群組的成員只能搜尋對該屬性具有特定值之使用者的內容位置。這是您限制誰可以搜尋特定機構中內容的方式。

>[!NOTE]
>目前，您必須對商務用 OneDrive 執行額外步驟，並將 Microsoft 支援服務歸檔，讓屬性同步至商務用 OneDrive 帳戶。

4. 在安全性與合規性中心，對每一個合規性界限建立系統管理員角色群組。我們建議您複製內建的電子文件探索管理員角色群組，然後視需要移除任何角色，來建立這些角色群組。

5. 請將成員新增至每個特定角色群組，作為電子文件探索管理員。 成員將是負責調查並回應 DSR 的人員，而且通常包括 IT 系統管理員、資料隱私權主管、合規性管理員，以及人力資源代表。

6. 請建立每個合規性界限的搜尋權限篩選器，如此對應的系統管理員角色群組成員，就只能搜尋該機構/合規性界限規內使用者的信箱和網站。 搜尋權限篩選器會讓對應的角色群組成員，只能搜尋使用者物件屬性值對應至機構/合規性界限的內容位置。

如需逐步指示，請參閱[設定 Office 365 中電子文件探索調查的合規性界限](https://support.office.com/article/1b45c82f-26c8-44fb-9f3b-b45436fe2271)。

### <a name="use-the-audit-log-search-tool-in-dsr-investigations"></a>在 DSR 調查時使用稽核記錄搜尋工具

IT 系統管理員可以使用安全性與合規性中心的稽核記錄搜尋工具，來識別使用者已建立、存取、變更或刪除的文件、檔案和其他 Office 365 資源。搜尋此類型的活動有助於 DSR 調查。例如，在 SharePoint Online 和商務用 OneDrive 中，使用者執行下列活動時，會記錄稽核事件：

- 已存取檔案
- 已修改檔案
- 已移動檔案
- 已上傳或下載檔案

您可以搜尋特定活動的稽核記錄、活動類型、特定使用者所執行的活動，以及其他搜尋準則。 除了 SharePoint Online 和商務用 OneDrive 活動外，您也可以搜尋 Flow、Power BI 和 Microsoft Teams 中的活動。 稽核記錄會保留 90 天。 因此，您將無法搜尋 90 天以前發生的使用者活動。 如需稽核活動的完整清單，以及如何搜尋稽核記錄，請參閱[搜尋安全性與合規性中心的稽核記錄](search-the-audit-log-in-security-and-compliance.md)。

>[!TIP]
>若要解決上述的 90 天限制，並維護貴組織稽核記錄的執行歷程記錄，您可以根據週期性排程 (例如，每隔 30 天) 匯出所有活動，以具有貴組織稽核記錄的連續記錄。

## <a name="appendix-b-change-log"></a>附錄 B：變更記錄

下表列出自從 2018 年 5 月 25 日首次發行之後，Office 365 DSR 指南中所做的變更。

|日期  |章節/應用程式 |變更  |
|:---------|:---------|:---------|
|9/18/2018 | [Whiteboard](#whiteboard) |「Whiteboard 預覽」不再是預覽狀態，並且已發行正式運作。因此，「Whiteboard 預覽」的章節會重新命名為「適用於電腦、Surface Hub 及其他平台的 Whiteboard」；存取、匯出及刪除資料的程序將會從這個章節中移除，以連結至 Whiteboard 支援文章的連結取代。|
|11/08/2018 | [工作場所分析](#workplace-analytics) |已為「刪除」一節新增逐步指引，其中包括如何從工作場所分析移除資料主體，以及如何從工作場所分析報告中移除資料主體的相關資訊。|
|11/12/2018| 全部| 已修復損毀的書籤及損毀的外部主題連結。|
|1/9/2019| StaffHub |在 [刪除] 區段中，更新了使用者帳戶遭到永久刪除時將會發生什麼情況的描述。|
|2019 年 5 月 8 日| [Publisher](#publisher)|新增有關針對 Publisher 回應 DSR 的內容。|
|2019 年 7 月 11 日| [MyAnalytics](#myanalytics)|因為所有使用者都能在 MyAnalytics 應用程式中檢視自己的資料，所以已移除系統管理員在安全性與合規性中心內使用 DSR 個案工具以匯出 MyAnalytics 資料的能力。 |
|2019/11/6|[教育](#education)|連結至使用 PowerShell 指令碼取得特定學生的課程清單，然後匯出或刪除其資料的新主題。|
|2020/1/28| 全部 | 已從文件中移除 StaffHub，StaffHub 已淘汰。 |
||||
