---
title: GDPR 的 Intune 資料主體要求
description: 本指南會介紹如何使用 Microsoft 產品、服務及系統管理工具，協助我們的控制者客戶找出並處理個人資料，以回應 DSR 要求。
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
author: dougeby
manager: angrobe
audience: itpro
ms.collection: GDPR
hideEdit: true
ms.openlocfilehash: 01f30dfbeb851731b6a8a101e19101b8f446524f
ms.sourcegitcommit: d9e9788abb31f6c876f81326569ccc9b716fc1c0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/08/2019
ms.locfileid: "37422280"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a>GDPR 的 Intune 資料主體要求

歐盟[一般資料保護規定 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 賦予人們 (在此法規中稱為*資料主體*) 權利來管理雇主或其他類型的代理機構或組織 (稱為*資料控制者*或僅稱為*控制者*) 所收集的個人資料。 依據 GDPR，個人資料的定義非常廣泛，舉凡與已識別或可識別自然人相關的任何資料皆屬之。 GDPR 為資料主體提供其個人資料的特定權限；這些權限包括取得個人資料副本、要求對該資料進行更正、限制對該資料的處理、刪除該資料，或是以電子格式接收該資料以移至另一個控制者。 由資料主體向控制者提出以對其個人資料採取行動的正式要求，稱為*資料主體要求*或 DSR。

本指南會討論如何使用 Microsoft 產品、服務及系統管理工具，協助我們的控制者客戶找出並對個人資料採取動作，以回應 DSR；尤其是針對如何找出、存取與處理在 Microsoft 雲端中常駐的個人資料。以下是本指南中所述程序的快速概觀：

- **探索**：使用搜尋和探索工具，更輕鬆地尋找可能成為 DSR 主體的客戶資料。 收集到可能的回應文件之後，您就可以執行下列步驟中所述的一或多個 DSR 動作來回應要求。 或者，您可能判定該要求不符合組織回應 DSR 的方針。
- **存取：** 擷取在 Microsoft 雲端中常駐的個人資料，並在要求時製作可供資料主體使用的副本。
- **修正：** 在適用情況下，對個人資料進行變更或實行其他要求的動作。
- **限制**：藉由盡可能移除各種 Azure 服務的授權或關閉所需的服務，以限制個人資料的處理。 您也可以從 Microsoft 雲端移除資料，並將它保留在內部部署或另一個位置。
- **刪除：** 將會永久移除 Microsoft 雲端中常駐的個人資料。
- **匯出：** 將個人資料的電子副本 (以機器可讀取的格式) 提供給資料主體。

本指南中的每一節說明資料控制者組織可以採取的程序，以回應對 Microsoft 雲端中個人資料的 DSR。

#### <a name="terminology"></a>術語

以下提供與本指南相關的詞彙定義。

- **控制者：** 自然人或法人、公家機關、公司或其他主體，不論單獨或與其他單位聯合，會決定處理個人資料的用途以及方式，其中此類處理的用途以及方式是由聯盟與成員國法律所決定，控制者人選或提名控制者的特定準則可由聯盟與成員國法律提供。
- **個人資料和資料主體：** 表示與已識別或可識別之自然人 (以下稱為「資料主體」) 相關的任何資訊；可識別的自然人是可以直接或間接識別的人員，尤其是藉由參照如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身分等一個或多個識別碼來識別。
- **處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。
- **客戶資料：** 由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。 客戶資料包括 (1) 使用者的識別資訊 (例如 Azure Active Directory 中的使用者名稱和連絡人資訊)，以及客戶上傳到特定服務或在特定服務中建立的客戶內容 (例如，Azure 儲存體帳戶中的客戶內容、Azure SQL Database 的客戶內容，或 Azure 虛擬機器中客戶的虛擬機器映像)。
- **系統產生的記錄：** Microsoft 產生的記錄及相關資料，可協助 Microsoft 向使用者提供企業服務。 系統產生的記錄主要包含經過假名化處理的資料 (例如唯一識別碼)，一般是由系統所產生的數字，無法單獨用來識別個人，但可用來向使用者提供企業服務。 系統產生的記錄也可能包含使用者的身分識別資訊 (例如使用者名稱)。

#### <a name="how-to-use-this-guide"></a>如何使用本指南

本指南包含兩個部分：

- **第 1 部分：回應資料主體對客戶資料的要求：** 本指南中的第 1 部分討論了如何從您所撰寫資料的應用程式中，存取、修正、限制、刪除以及匯出資料。 本節將詳細說明如何針對客戶內容以及使用者的可識別資訊執行 DSR。
- **第 2 部分：回應資料主體對系統所產生記錄檔的要求：** 當您使用 Microsoft 企業服務時，Microsoft 會產生某些資訊 (稱為「系統產生的記錄檔」) 以提供服務。 本指南中的第 2 部分將討論如何針對 Azure 來存取、刪除及匯出這類資訊。

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>了解 Azure Active Directory 和 Microsoft Intune 的 DSR

在考慮為企業客戶所提供的服務時，請務必了解要在指定的 Azure Active Directory (AAD) 範圍內執行 DSR。值得注意的是，DSR 一律會在指定的 AAD 租用戶中執行。如果使用者參與了多個租用戶，請務必強調特定的 DSR「只能」** 在接收到要求的指定租用戶範圍內執行。請務必了解這點，因為這代表由某個企業客戶所執行的 DSR **不會**影響相鄰企業客戶的資料。

這點同樣也適用於提供給企業客戶的 Microsoft Intune：對「與 AAD 租用戶相關聯的」** Intune 帳戶所執行的 DSR，**只會**針對租用戶中的資料。此外，在處理租用戶中的 Intune 帳戶時，請務必了解下列事項：

- 若 Intune 使用者建立了 Azure 訂用帳戶，我們會將該訂用帳戶視為 AAD 租用戶來處理。因此，DSR 的範圍會限制在租用戶內，如上所述。
- 若您刪除了透過 Intune 帳戶所建立的 Azure 訂用帳戶，**將不會影響到**實際的 Intune 帳戶。同樣地，如上所述，在 Azure 訂用帳戶中所執行的 DSR，會限制在租用戶本身的範圍內。

**在指定的租用戶外**，對 Intune 帳戶本身所執行的 DSR，會透過消費者隱私權儀表板來執行。請參閱《Windows 資料主體要求指南》以取得詳細資訊。

## <a name="part-1-dsr-guide-for-customer-data"></a>第 1 部分：客戶資料的 DSR 指南

### <a name="executing-dsrs-against-customer-data"></a>針對客戶資料執行 DSR

Microsoft 透過 Azure 入口網站，提供了存取、刪除及匯出特定客戶資料的功能；您也可直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI) 來執行上述功能 (也稱為「產品內體驗」**)。在上述服務各自的參考文件中有詳細資料，說明這類的產品內體驗。

>[!IMPORTANT]  
>支援產品內 DSR 的服務需要直接使用服務的應用程式開發介面 (API) 或使用者介面 (UI)，來描述適用的 CRUD (建立、讀取、更新、刪除) 作業。因此，除了在 Azure 入口網站中執行 DSR 以外，還必須另外在指定的服務中執行 DSR，才能完成指定資料主體的完整要求。請參閱特定服務的參考文件，以取得詳細資訊。

### <a name="step-1-discover"></a>步驟 1：探索

回應 DSR 的第一個步驟是先找出個人資料，也就是要求的主體。第一個步驟 (尋找並檢閱上述的個人資料)，可協助您判斷 DSR 是否符合貴組織的需求，以便接受或拒絕。第一個步驟 (尋找並檢閱上述的個人資料)，可協助您判斷 DSR 是否符合貴組織的需求，以便接受或拒絕。例如，在找出並檢閱個人資料後，您可能因為這樣做會對其他人的權利和自由造成負面影響，而判斷要求不符合貴組織的需求。

找到資料後，接著您可以執行特定動作來滿足資料主體的要求。如需詳細資訊，請參閱下列內容：

- [資料收集](https://docs.microsoft.com/intune/privacy-data-collect)
- [資料儲存和處理](https://docs.microsoft.com/intune/privacy-data-store-process)
- [檢視個人資料](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>步驟 2：存取

找到包含個人資料且可能會回應 DSR 的客戶資料之後，您與貴組織有權決定要將哪些資料提供給資料主體。您可以提供他們實際文件的副本、經過適當刪減的版本，或您認為適合分享的部分螢幕擷取畫面。對於這些存取要求的每項回應，您都必須擷取一份文件副本，或其他包含回應資料的項目。

當您提供複本給資料主體時，可能需要移除或刪減關於其他資料主體的個人資訊，以及任何機密資訊。

以下說明如何取得資料副本以便回應 DSR 存取要求。

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft 提供入口網站與產品內體驗，讓企業客戶的租用戶系統管理員能夠管理 DSR 存取要求。 DSR 存取要求可允許針對下列使用者個人資料進行存取，包括：(a) 使用者的識別資訊和 (b) 系統產生的記錄檔。

#### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft Intune 能夠透過使用者介面 (UI) 或既有的應用程式開發介面 (API) 直接[探索客戶資料](#step-1-discover)。

### <a name="step-3-rectify"></a>步驟 3：修正

若資料主體要求您修正貴組織資料中常駐的個人資料，您和貴組織需要判斷是否適合接受要求。修正資料可能包含採取下列動作，例如：從文件或其他類型的項目中，編輯、刪減或移除個人資料。

身為資料處理者，Microsoft 不提供對系統所產生記錄檔的更正功能；因為這個功能可反映出實際的活動，並構成 Microsoft 服務中所發生事件的歷史記錄。至於 Intune，系統管理員無法更新裝置或應用程式特定的資訊。若使用者需要修正任何個人資料 (如裝置名稱)，則必須直接在其裝置上進行修正。下次當使用者連線至 Intune 時，系統即會同步這些變更。

### <a name="step-4-restrict"></a>步驟 4：限制

資料主體可能會要求您只能處理他們的個人資料。 我們提供 Azure 入口網站與既有的應用程式開發介面 (API) 兩者，或使用者介面 (UI)。 這些體驗能夠讓企業客戶的租用戶系統管理員，透過匯出資料和刪除資料的組合功能管理這類 DSR。 如需詳細資訊，請參閱[處理個人資料](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data)。

### <a name="step-5-delete"></a>步驟 5：刪除

從組織的客戶資料中移除其個人資料的「抹除的權利」，是 GDPR 中的關鍵保護機制。這是指移除個人資料，包括移除稽核記錄資訊以外的所有個人資料和系統所產生的記錄。如需詳細資訊，請參閱[刪除使用者個人資料](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data)。

## <a name="part-2-system-generated-logs"></a>第 2 部分：系統所產生的記錄檔

稽核記錄會向租用戶系統管理員提供活動記錄，其會在 Microsoft Intune 中產生變更。稽核記錄可供許多管理活動使用，且通常會建立、更新 (編輯)、刪除及指派動作。還可以檢閱產生稽核事件的遠端工作。這些稽核記錄可能包含使用者個人資料，而這些使用者的裝置已在 Intune 中加以註冊。系統管理員無法刪除稽核記錄。如需詳細資訊，請參閱[稽核個人資料](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data)。

## <a name="notify-about-exporting-or-deleting-issues"></a>匯出或刪除問題的通知

如果您從 Azure 入口網站匯出或刪除資料時遇到問題，請前往 Azure 入口網站 [協助 + 支援]**** 刀鋒視窗，並在 [訂閱管理 > 其他安全性和法規遵循要求> 隱私權刀鋒視窗和 GDPR 要求]**** 下提交新票證。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)