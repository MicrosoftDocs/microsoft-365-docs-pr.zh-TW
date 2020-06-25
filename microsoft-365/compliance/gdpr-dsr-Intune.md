---
title: GDPR 和 CCPA 的 Intune 資料主體要求
description: 瞭解如何使用 Microsoft Intune 以尋找並處理個人資料，並回應客戶提出的 DSR 和 CCPA 要求。
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
ms.custom:
- seo-marvel-mar2020
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a9dd161edd740aa97e97afa02a6c53933a6ac211
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817652"
---
# <a name="intune-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的 Intune 資料主體要求

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.

同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。  CCPA 也提供特定揭露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。 銷售的廣泛定義，包括出於有價值的考量而共用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

本指南會討論如何使用 Microsoft 產品、服務及系統管理工具，協助我們的控制者客戶找出並處理個人資料，以回應 DSR。 具體而言，這包括如何尋找、存取及處理位於 Microsoft 雲端的個人資料或個人資訊。 以下是本指南中所述程序的快速概觀：

- **探索**：使用搜尋和探索工具，更輕鬆地尋找可能成為 DSR 主體的客戶資料。 收集到可能的回應文件之後，您就可以執行下列步驟中所述的一或多個 DSR 動作來回應要求。 或者，您可能判定該要求不符合組織回應 DSR 的方針。
- **存取：** 擷取在 Microsoft 雲端中常駐的個人資料，並在要求時製作可供資料主體使用的副本。
- **修正：** 在適用情況下，對個人資料進行變更或實行其他要求的動作。
- **限制**：藉由盡可能移除各種 Azure 服務的授權或關閉所需的服務，以限制個人資料的處理。 您也可以從 Microsoft 雲端移除資料，並將它保留在內部部署或另一個位置。
- **刪除：** 永久移除 Microsoft 雲端中常駐的個人資料。
- **匯出/接收 (可攜性)：** 將個人資料或個人資訊以電子複本 (以電腦可讀取的格式) 提供給資料主體。 CCPA 中的個人資訊是任何與已識別或可識別個人相關的資訊。 個人的私人、公開或工作角色之間沒有區別。 定義的「個人資訊」一詞大致與 GDPR 下的「個人資料」對應。 不過，CCPA 也包含家庭和家用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

本指南中的每一節說明資料控制者組織可以採取的程序，以回應對 Microsoft 雲端中個人資料的 DSR。

#### <a name="terminology"></a>術語

以下提供與本指南相關的詞彙定義。

- **控制者：** 自然人或法人、公家機關、公司或其他主體，不論單獨或與其他單位聯合，會判斷處理個人資料的用途以及方式，其中此類處理的用途以及方式的判斷是根據聯盟與成員國法律，控制者人選或提名控制者的特定準則可由聯盟與成員國法律提供。
- **個人資料和資料主體：** 表示與已識別或可識別之自然人 (以下稱為「資料主體」) 相關的任何資訊；可識別的自然人是可以直接或間接識別的人員，尤其是藉由參照如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身分等一個或多個識別碼來識別。
- **處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。
- **客戶資料：** 由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。 客戶資料包括 (1) 使用者的識別資訊 (例如 Azure Active Directory 中的使用者名稱和連絡人資訊)，以及客戶上傳到特定服務或在特定服務中建立的客戶內容 (例如，Azure 儲存體帳戶中的客戶內容、Azure SQL Database 的客戶內容，或客戶在 Azure 虛擬機器中的虛擬機器映像)。
- **系統產生的記錄：** Microsoft 產生的記錄及相關資料，可協助 Microsoft 向使用者提供企業服務。 系統產生的記錄主要包含經過假名化處理的資料 (例如唯一識別碼)，一般是由系統所產生的數字，無法單獨用來識別個人，但可用來向使用者提供企業服務。 系統產生的記錄也可能包含使用者的身分識別資訊 (例如使用者名稱)。

#### <a name="how-to-use-this-guide"></a>如何使用本指南

本指南包含兩個部分：

- **第 1 部分：回應資料主體對客戶資料的要求：** 本指南中的第 1 部分討論了如何從您所撰寫資料的應用程式中，存取、修正、限制、刪除以及匯出資料。 本節將詳細說明如何針對客戶內容以及使用者的可識別資訊執行 DSR。
- **第 2 部分：回應資料主體對系統所產生記錄檔的要求：** 當您使用 Microsoft 企業服務時，Microsoft 會產生某些資訊 (稱為「系統產生的記錄檔」) 以提供服務。 本指南中的第 2 部分將討論如何針對 Azure 來存取、刪除及匯出這類資訊。

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>了解 Azure Active Directory 和 Microsoft Intune 的 DSR

When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.

The same also applies for Microsoft Intune provided to an enterprise customer: execution of a DSR against an Intune account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling Intune accounts within a tenant:

- If an Intune user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.
- If an Azure subscription created via an Intune account is deleted, **it will not affect** the actual Intune account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.

DSRs against an Intune account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.

## <a name="part-1-dsr-guide-for-customer-data"></a>第 1 部分：客戶資料的 DSR 指南

### <a name="executing-dsrs-against-customer-data"></a>針對客戶資料執行 DSR

Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services' reference documentation.

>[!IMPORTANT]  
>Services supporting in-product DSRs require direct usage of the service's application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services' reference documentation for further details.

### <a name="step-1-discover"></a>步驟 1：探索

The first step in responding to a DSR is to find the personal data that is the subject of the request. This first step - finding and reviewing the personal data at issue - will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR. For example, after finding and reviewing the personal data at issue, you may determine the request doesn't meet your organization's requirements because doing so may adversely affect the rights and freedoms of others.

After you find the data, you can then perform the specific action to satisfy the request by the data subject. For details, see the following:

- [資料收集](https://docs.microsoft.com/intune/privacy-data-collect)
- [資料儲存和處理](https://docs.microsoft.com/intune/privacy-data-store-process)
- [檢視個人資料](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>步驟 2：存取

After you've found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.

當您提供複本給資料主體時，可能需要移除或刪減關於其他資料主體的個人資訊，以及任何機密資訊。

以下說明如何取得資料副本以便回應 DSR 存取要求。

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft 提供入口網站與產品內體驗，讓企業客戶的租用戶系統管理員能夠管理 DSR 存取要求。 DSR 存取要求可允許針對下列使用者個人資料進行存取，包括：(a) 使用者的識別資訊和 (b) 系統產生的記錄檔。

#### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft Intune 能夠透過使用者介面 (UI) 或既有的應用程式開發介面 (API) 直接[探索客戶資料](#step-1-discover)。

### <a name="step-3-rectify"></a>步驟 3：修正

If a data subject has asked you to rectify the personal data that resides in your organization's data, you and your organization will have to determine whether it's appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item.

As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Intune, admins can't update device or app specific information. If an end user wants to correct any personal data (like the device name), they must do so directly on their device. Such changes are synchronized the next time they connect to Intune.

### <a name="step-4-restrict"></a>步驟 4：限制

資料主體可能會要求您只能處理他們的個人資料。 我們提供 Azure 入口網站與既有的應用程式開發介面 (API) 兩者，或使用者介面 (UI)。 這些體驗能夠讓企業客戶的租用戶系統管理員，透過匯出資料和刪除資料的組合功能管理這類 DSR。 如需詳細資訊，請參閱[處理個人資料](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data)。

### <a name="step-5-delete"></a>步驟 5：刪除

The "right to erasure" by the removal of personal data from an organization's Customer Data is a key protection in the GDPR. Removing personal data includes removing all personal data and system-generated logs, except audit log information. For details, see [Delete end user personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).

## <a name="part-2-system-generated-logs"></a>第 2 部分：系統所產生的記錄檔

Audit logs provide tenant admins with a record of activities that generate a change in Microsoft Intune. Audit logs are available for many manage activities and typically create, update (edit), delete, and assign actions. Remote tasks that generate audit events can also be reviewed. These audit logs may contain personal data from users whose devices are enrolled in Intune. Admins can't delete audit logs. For details, see [Audit personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).

## <a name="notify-about-exporting-or-deleting-issues"></a>匯出或刪除問題的通知

如果您從 Azure 入口網站匯出或刪除資料時遇到問題，請前往 Azure 入口網站 [協助 + 支援]**** 刀鋒視窗，並在 [訂閱管理 > 其他安全性和法規遵循要求> 隱私權刀鋒視窗和 GDPR 要求]**** 下提交新票證。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
