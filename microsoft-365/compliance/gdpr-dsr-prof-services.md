---
title: GDPR 和 CCPA 的 Microsoft 支援服務與專業服務資料主體要求
description: Microsoft 支援服務與專業服務如何處理 GDPR 和 CCPA 資料主體要求。
keywords: 專業服務, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR, CCPA
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
ms.openlocfilehash: bb16c663258647989c4b0ad3ca7f95f857e8a680
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632494"
---
# <a name="microsoft-support-and-professional-services-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的 Microsoft 支援服務與專業服務資料主體要求

## <a name="introduction-to-microsoft-professional-services"></a>Microsoft 專業服務簡介

Microsoft 專業服務包括一組多元化的技術結構設計師、工程師、顧問師，以及致力於達成 Microsoft 任務的支援專業人員，以期讓客戶更有能力與成就。我們的專業服務小組總計包括超過 21,000 名顧問師、數位顧問、頂級支援、工程師和專業銷售人員，這些專業人員在全球 191 個國家/地區工作，可支援 46 種不同的語言，每個月管理數百萬件約定，以及透過內部部署、電話、網路、社群和自動化工具參與客戶與合作夥伴互動。該組織具備廣泛的 Microsoft 產品組合專業知識，並運用廣闊的合作夥伴、技術社群、工具、診斷及通道網路來連結我們與企業客戶。

移至 [Microsoft 專業服務安全性文件網頁](https://www.microsoft.com/en-us/professionalservices/overview)，以深入了解 Microsoft 專業服務。 Microsoft 專業服務很認真看待其在一般資料保護規定 (GDPR) 下所需承擔的責任。 本文件中的資訊是為了回答客戶有關 Microsoft 的支援和諮詢供應項目如何根據 GDPR 回應及協助客戶回應資料主體要求 (DSR) 義務的問題。

### <a name="introduction-to-dsrs"></a>DSR 簡介 

GDPR 賦予人員 (在規範中稱為「資料主體」**) 權限，以管理由雇主或其他類型的公司或組織 (稱為「資料控制者」** 或簡稱「控制者」**) 收集而來的個人資料。個人資料在 GDPR 中的定義非常廣泛，係指與已識別或可識別自然人相關的任何資料。GDPR 賦予資料主體對其個人資料的特定權限，這些權限包括取得個人資料複本、要求更正資料、限制資料的處理和刪除資料。由資料主體向控制者提出對其個人資料採取某項動作的正式要求，稱為「資料主體要求」** 或 DSR。此外，它規定公司代表控制者 (稱為「資料處理者」** 或「處理者」**) 合理協助控制者達成 DSR。

同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。  CCPA 也提供特定接露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。 銷售的廣泛定義，包括出於有價值的考量而共用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

本指南說明如何尋找、存取及處理存在 Microsoft IT 系統的個人資料，這些資料經收集用以提供支援和其他專業服務產品。

在開發 DSR 的回應時，Microsoft 的客戶請務必了解，支援及諮詢資料與線上服務的客戶資料或其資料主體可能提供給 Microsoft 的其他資料是分開的。為線上服務提供的工具和程序、Microsoft 隱私權儀表板或其他用於回應 DSR 的 Microsoft 系統無法用來回應由 Microsoft 支援服務或其他專業服務持有的個人資料之 DSR。

所有要求必須透過支援人員進行，如下所述。目前沒有自助工具供客戶在專業服務組織內存取個人資料。

#### <a name="overview-of-the-processes-outlined-in-this-guide"></a>本指南中所述程序的概觀

- **探索**：使用搜尋和探索工具，更輕鬆地尋找可能成為 DSR 主體的客戶資料。 收集到可能的回應文件之後，您就可以執行下列步驟中所述的一或多個 DSR 動作來回應要求。 或者，您可能判定該要求不符合組織回應 DSR 的方針。
- **存取：** 擷取在 Microsoft 雲端中常駐的個人資料，並在要求時製作可供資料主體使用的副本。
- **修正：** 在適用情況下，對個人資料進行變更或實行其他要求的動作。
- **限制**：藉由盡可能移除各種 Azure 服務的授權或關閉所需的服務，以限制個人資料的處理。 您也可以從 Microsoft 雲端移除資料，並將它保留在內部部署或另一個位置。
- **刪除：** 永久移除 Microsoft 雲端中常駐的個人資料。
- **匯出/接收 (可攜性)：** 將個人資料或個人資訊以電子複本 (以電腦可讀取的格式) 提供給資料主體。 CCPA 中的個人資訊是任何與已識別或可識別個人相關的資訊。 個人的私人、公開或公司角色之間沒有區別。 定義的「個人資訊」一詞在 GDPR 下，大致與「個人資料」相符。 不過，CCPA 也包含家庭和家用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](offering-ccpa.md)和[常見問題集](ccpa-faq.md)。

### <a name="terminology"></a>術語

以下是來自 GDPR 與本指南相關之詞彙的定義：

- **控制者：** 自然人或法人、公家機關、公司或其他主體，不論單獨或與其他單位聯合，會判斷處理個人資料的用途以及方式，其中此類處理的用途以及方式的判斷是根據聯盟與成員國法律，控制者人選或提名控制者的特定準則可由聯盟與成員國法律提供。
- **個人資料和資料主體：** 表示與已識別或可識別之自然人 (以下稱為「資料主體」) 相關的任何資訊；可識別的自然人是可以直接或間接識別的人員，尤其是藉由參照如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身分等一個或多個識別碼來識別。
- **處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。

#### <a name="additional-terms-and-definitions-that-may-be-helpful-in-understanding-this-guide"></a>有助於了解本指南的其他術語和定義

- **支援和查閱資料：** 包括所有文字、音訊、視訊、影像檔或軟體的所有資料，由客戶或代表客戶 (或客戶授權 Microsoft 以從線上服務取得) 提供給 Microsoft，透過與 Microsoft 的約定以取得支援或專業服務。 若要釐清，這不包括 Microsoft 是資料控制者時收集的資料，包括客戶連絡人資料。
- **客戶連絡人：** 個人資料可能是您與 Microsoft 商務關係的其中一部分，例如客戶連絡人資訊中包含的個人資料。 這可能包括您的名稱、電子郵件或主要合約服務管理員 (CSM) (線上服務的全域或 IT 系統管理員，或類似角色) 的電話號碼。
- **假名化資料**當您對 Microsoft 企業產品和服務使用 Microsoft 支援時，Microsoft 會產生一些資訊，其連結至 Microsoft 數字識別碼以提供支援。 這通常稱為「假名化資料」。雖然若未使用其他資訊時，此資料並不屬於特定資料主體，但是在 GDPR 對個人資料的廣泛定義下，其中某部分可能會被視為個人資料。 在專業服務中，達成或協助達成 DSR 的要求一律會自動包含處理假名化資料。

### <a name="how-to-use-this-guide"></a>如何使用本指南

本指南包含若客戶使用 Microsoft 專業服務可能會遇到的四個案例。

- **Microsoft 客戶連絡人的 DSR：** 說明 Microsoft 會如何回應客戶連絡人或 IT 系統管理員的要求來執行資料主體權利。
- **使用者參與 Microsoft 的 DSR：** 說明 Microsoft 會如何回應客戶員工或其他資料主體的要求來執行其權利。
- **客戶提供資料的 DSR：商業支援：** 說明當客戶收到員工或其他資料主體的要求要執行權限，且該資料主體的個人資料在支援約定期間由 Microsoft 支援服務所收集，在此情況下如何接收 Microsoft 的協助。
- **客戶提供資料的 DSR：諮詢服務包含 FastTrack 移轉服務：** 說明當客戶收到員工或其他資料主體的要求要執行權限，且該資料主體的個人資料在諮詢互動期間由 Microsoft 所收集時，在此情況下如何接收 Microsoft 的協助。

## <a name="dsr-for-a-customer-contact-engaging-microsoft"></a>Microsoft 客戶連絡人的 DSR

Microsoft 會如何回應客戶連絡人或 IT 系統管理員的要求來執行資料主體權利。**

當客戶與 Microsoft 約定以接收支援或諮詢服務時，Microsoft 支援服務會自動收集或從帳戶記錄中擷取客戶連絡人 (例如主要 CSM、全域系統管理員、IT 系統管理員) 的個人資料。 這可能包括名稱、電子郵件、電話和尋求支援或諮詢服務的個體之其他個人資料。

客戶連絡人的個人資料是 Microsoft 與客戶商務關係的一部分，且 Microsoft 是資料控制者。Microsoft 會回應客戶連絡人有關其個人資料的 DSR，無論其是否仍在組織中。

客戶應了解，DSR 只涵蓋客戶連絡人的個人資料，且不會變更或刪除提交為約定 (例如文字記錄、案例說明、檔案、工作產品) 一部分的任何客戶資料，因為 Microsoft 是資料處理者。 此外，為維護約定的歷程記錄，不會對已結束的約定進行任何變更，包括開啟約定者的記錄。

從客戶連絡人收到有關 DSR 的查詢時，Microsoft 人員會將客戶連絡人送交給[隱私權回應中心](https://go.microsoft.com/fwlink/?LinkId=321116)。這是 Microsoft 對隱私權查詢和抱怨的主要輸入機制。在收到查詢時，隱私權回應中心會識別其屬於商業或組織帳戶，並據此回應。

為維護客戶的業務連續性，Microsoft 在確認取代的連絡人之前不會處理與約定相關的 DSR。在確認新連絡人後，Microsoft 會在開放約定中將舊連絡人換為新連絡人。

客戶可以選擇透過一般支援或諮詢管道 (與此 DSR 不同) 對於在專業服務約定期間所收集的資料進行變更。舉例來說，經要求 Microsoft 可以協助刪除支援約定 (請參閱下面一節*客戶所提供資料的 DSR 指南*)。

***僅供說明的範例***

John 是 O365 企業客戶的 IT 系統管理員，具有一個開放支援約定與兩個已結束的約定。現在 John 要離開公司，並希望刪除其資料。John 先連絡隱私權回應中心，其將他識別為 IT 系統管理員，並告知其名稱無法從先前 (已結束) 的約定或從開放約定內的任何資料中刪除。不過，如果 John 找到取代的連絡人，隱私權回應中心會將目前開放支援票證的連絡人更改為取代連絡人。John 讓 Microsoft 知道了 Jane 會成為取代的連絡人，Microsoft 即在所有支援系統上進行變更。

## <a name="dsr-for-an-end-user-engaging-microsoft"></a>Microsoft 使用者的 DSR

Microsoft 會如何回應客戶員工或其他資料主體的要求來執行其權利。**

如果客戶員工或其他資料主體與 Microsoft 連絡，以針對 Microsoft 以資料處理者身分收集的資料執行其權限，則該資料主體會被告知他們需要連絡 Microsoft 客戶 (資料控制者)，以執行這些權限。Microsoft 不會採取進一步的動作。

如果資料主體也與 Microsoft 連絡，以針對在 Microsoft 為資料控制者 (例如家庭用戶支援、商業客戶連絡人) 情況下所收集的資料執行其權限，則 Microsoft 會分別回應個人資料的資料主體權限要求。

***僅供說明的範例***

珮雯是企業客戶的員工，Contoso 已授予她 Dynamics 365 帳戶的權限。 她連絡 Microsoft 要求將其所有資料刪除，並轉介至隱私權回應中心。 珮雯填寫了要求表單。 隱私權回應中心識別其具有企業使用者身分，並告知她必須透過 Contoso 才能刪除其企業資料。 隱私權回應中心同時也識別出她是 Microsoft X-Box 使用者，並刪除其家庭用戶 Microsoft 帳戶中的資料。

## <a name="dsr-for-customer-provided-data-commercial-support"></a>客戶所提供資料的 DSR：商業支援

當客戶收到員工或其他資料主體的要求要執行權限，且該資料主體的個人資料在支援約定期間由 Microsoft 支援服務所收集，在此情況下如何接收 Microsoft 的協助。**

當客戶與 Microsoft 支援服務約定時，Microsoft 會收集客戶的支援資料以解決需要支援約定的任何問題。 這項支援資料包含 Microsoft 與客戶的互動 (例如聊天、電話、電子郵件、網頁提交)，加上客戶傳送給 Microsoft，或 Microsoft 經客戶同意從客戶 IT 環境或線上服務租用戶擷取的任何內容檔案，用以解決支援問題。 在主要支援的情況下，這還會包含我們向您收集的任何資料，以主動預防日後問題。 不過，這會排除客戶連絡人資訊或 Microsoft 與客戶商務關係 (例如帳單記錄) 的其他資訊。

對於所有支援資料，Microsoft 都是資料處理者。因此，Microsoft 不會回應資料主體針對與 Microsoft 商業客戶相關聯時提供的支援資料的直接要求。Microsoft 會透過客戶的一般支援管道協助客戶回應 DSR。

## <a name="step-1-discover"></a>步驟 1：探索

取得 Microsoft 的協助以回應 DSR 的第一個步驟，是先找出個人資料，也就是 DSR 的主體。 第一個步驟 (尋找並檢閱上述的個人資料)，可協助客戶判斷 DSR 是否符合貴組織的需求，以便接受或拒絕。第一個步驟 (尋找並檢閱上述的個人資料)，可協助您判斷 DSR 是否符合用於遵循資料主體要求的貴組織原則，以便接受或拒絕。

在客戶找出資料後，可以執行特定動作，以滿足資料主體的要求。客戶嘗試執行的動作將會決定客戶需要進行的探索層級。

在 Microsoft 協助客戶解決 DSR 時，這是商業功能，且要求是透過標準支援管道進行，而非透過向隱私權回應中心的要求。

在探索相關資料及取得 Microsoft 的協助方面，對於如何達到 DSR 客戶有數種選項：

選項 A：跨 Microsoft 支援服務客戶 DSR**。將 DSR 套用於 Microsoft 支援環境中所有客戶的支援資料。若要這麼做，客戶可以要求 Microsoft 將 DSR 套用於收集的所有支援資料。

*選項 B — 特定客戶參與。* 使用線上系統檢閱工單，然後找出特定的約定，其中包含相關的個人資料並向 Microsoft 報告。 如果客戶無法搜尋約定 (工單)，Microsoft 會嘗試提供協助以執行搜尋。

***識別出約定之後，要求將 DSR 套用於記錄的特定部分，或 Microsoft 中與該約定相關的所有項目。***

若要找出特定的約定，客戶需要搜尋其約定。對於頂級客戶，客戶的合約服務管理員 (“CSM”) 可看見在該合約排程下建立的所有支援要求 (SR)。對於非頂級客戶，則提供對等的支援約定入口網站，例如透過線上服務支援區域。

![在 SMC 中搜尋](../media/Prof-Serv-DSR-Doc-Final_image3.png)CSM 可以進到入口網站 Support.Microsoft.Com ([https://support.microsoft.com/\<local語言代碼\>/頂級](https://support.microsoft.com/%3clocal%20language%20code%3e/premier)) ("SMC") 並選取及檢閱支援要求。 (請注意：在 URL 中請替代為您的當地語言代碼)。

>[!IMPORTANT]
>除了 SMC 中的案例歷程記錄，客戶也可擁有在支援約定期間由 Microsoft 收集 (或經客戶同意，從線上服務移除) 的使用者個人資料檔案。 例子包括客戶 exchange 信箱、Azure VM 或資料庫的複本。 此個人資料可能或不一定會在特定約定的案例歷程記錄 (亦即工單) 中述及。 若要檢閱該資料，客戶連絡人必須是特定的驗證 (透過 AAD 或 MSA) 支援要求連絡人，其已在 Microsoft 支援服務資料傳輸和管理工具 (DTM) 中收到工作區 URL。 客戶連絡人可存取檔案，但無法進行全域檢視，且 SMC 不會指出檔案是否存在。

當客戶已找出所選支援工單中的所有相關資料時，客戶可決定是否要求刪除與工單相關的所有項目，或選擇性將 DSR 套用到個人資料的個別執行個體。

## <a name="step-2-access"></a>步驟 2：存取

在客戶找到包含個人資料且可能會回應 DSR 的支援資料之後，客戶有權決定要在回應中包含哪些個人資料。比方說，客戶可以選擇移除有關其他資料主體和任何機密資訊的個人資料。

對 DSR 的回應可能包含實際文件的副本、經過適當刪減的版本，或客戶認為適合分享的部分螢幕擷取畫面。對於這些存取要求的每項回應，客戶都必須擷取一份文件副本，或其他包含回應資料的項目。

使用者個人資料的存取權可能來自不同類型內容文件中的相關記錄或註解。 由於客戶可能會存取約定工單和內容，因此客戶可以自己提供個人資料摘要，而不需要 Microsoft 進一步的協助。

在罕見的情況下，客戶可能需要取得 Microsoft 代表與客戶代表之間的支援互動資料 (例如電子郵件、電話記錄的謄寫複本、聊天文字記錄) 複本。 在所需範圍內，Microsoft 會根據需求、機密性和困難度，提供這些文字記錄經刪減過的複本。

## <a name="step-3-rectify"></a>步驟 3：修正

如果資料主體要求客戶修正存在組織支援資料中的個人資料，客戶必須判斷是否要接受要求。如果客戶選擇接受要求，則客戶可能會要求 Microsoft 進行變更。Microsoft 可能會修正資料，或從支援系統中刪除客戶的資料，並要求客戶以修正過的格式重新提交給 Microsoft。

## <a name="step-4-restrict"></a>步驟 4：限制

客戶隨時可能會結束約定，或連絡 Microsoft 要求結束約定。 已結束的約定可避免執行任何工作。

如需額外保證，客戶可能會與 Microsoft 連絡，並要求在約定工單系統中加上附註，表示該案件未經客戶同意不應重新開啟。

附註：根據資料、服務和系統的機密性，約定 (工單) 也會依照保留期與刪除排程一併刪除。 如果客戶需要資料副本，應先確認在刪除之前已擷取資料。

## <a name="step-5-delete"></a>步驟 5：刪除

從組織的支援資料中移除其個人資料的「抹除的權利」，是 GDPR 中的關鍵保護機制。 移除個人資料包括刪除整個約定、文件或檔案，或刪除約定、文件或檔案內的特定資料。

當客戶調查或準備刪除個人資料，以回應 DSR 時，以下是一些重要事項，讓您了解如何在 Microsoft 支援服務進行刪除。

Microsoft 的所有資料都有套用保留期與刪除原則，這些會根據風險及其他因素而有所不同。

若客戶要求跨支援系統刪除資料主體的個人資料，可透過 TAM 進行或在 SMC 或對等系統中填寫支援要求 (SR)。您*必須*指出此要求是協助您在 GDPR 下的 DSR。

*選項 A — 跨 Microsoft 支援客戶 DSR*。 針對跨系統 DSR，客戶必須提供 Microsoft 需要的個人資料，以識別所需資料 (例如電子郵件地址、電話號碼)。 Microsoft 不會建立相互關聯或研究記錄，而僅會在客戶所提供的識別項上直接進行搜尋。 找到資料時，Microsoft 就會刪除所有約定和所有相關資料。

> 重要注意事項：這可能會導致客戶組織的重要歷程記錄遺失。

*選項 B — 特定客戶參與*。 對於客戶找出並想刪除的特定約定，請勿刪除 SMC 的工單。 這會導致存在於記錄檔和下游系統中的個人資料無法在所需時間範圍內刪除。 相反地，找出必須刪除的工單或工單內的個人資料，並連絡 Microsoft 支援服務，以協助您刪除資料。

### <a name="microsoft-support-data-transfer-and-management-tool-dtm-instructions"></a>Microsoft 支援服務資料傳輸和管理工具 (DTM) 指示

對於所有這些搜尋，因為檔案內容潛在的機密性，Microsoft 不會搜尋 DTM。不過，如果客戶想要，Microsoft 會刪除包含在 DTM 中與客戶帳戶相關聯的所有檔案。由於可能造成重大的客戶影響，Microsoft 需要指定刪除 DTM 檔案的客戶個別要求。

- 對於開放的案件，客戶連絡人可以進入 DTM 並刪除檔案。
- 對於在 90 天內結束的案件，必須對 TAM 或 SR 提出要求以移除檔案。
- 對於結束超過 90 天的案件，檔案已自動刪除。
- 即使個人資料僅位於已刪除的檔案內，客戶仍必須讓 Microsoft 對系統執行個人資料檢查，因為某些資料可能在提供支援的過程中已從 DTM 移除。

## <a name="step-6-export"></a>步驟 6：匯出

「資料可攜性權限」可讓資料主體要求其個人資料的電子格式副本，並要求貴組織將資料傳送給其他控制者。在支援資料的情況下，Microsoft 擁有的任何可用資訊，其格式會是可傳回給您的約定資訊或檔案，以供重新通訊或上傳給其他控制者。

附註：匯出的資料不包含 Microsoft 的智慧財產或可能危及服務安全性或穩定性的任何資料。

***僅供說明的範例***

John 是企業客戶 Contoso 的主要 CSM，Contoso 使用 O365 做為員工電子郵件並使用 Azure 裝載 Contoso SQL 資料庫。Contoso 擁有多個開放及結束的工單。最近，Microsoft 支援服務在 Contoso 的同意下，將 SQL 資料庫副本移到 DTM 中，以進行支援與疑難排解。

John 收到 Jane 的 DSR，要求刪除她的所有資料。John 進入 SMC 並搜尋約定，發現 Jane 有電子郵件帳戶問題，因此其名稱和電子郵件地址參照在兩份工單中。他連絡了 TAM，提供 Jane 的名稱和電子郵件地址做為識別項，並要求刪除那兩份工單，以及可能由工單所產生的所有下游資料。

他也擔心他與支援人員提及 Jane 的聊天交談，因此要求刪除該聊天記錄。

他還知道 Jane 的個人資料位於 SQL 資料庫中。由於 SQL VM 在不到 90 天前已移至 DTM，他另外要求 TAM 協助從 DTM 中立即刪除資料庫。

最後，由於他知道資料可能在提供支援期間已經從 DTM 檔案中移除，他要求 Microsoft 在 IT 系統中對 SQL 資料庫中 Jane 的個人資料執行檢查。

Microsoft 支援服務執行了以上所有刪除，且根據客戶要求，TAM 也向他提供證明，聲明要求的資料皆已刪除。

## <a name="dsr-guide-for-customer-provided-data-in-consulting-services-including-migration-services"></a>諮詢服務中客戶所提供資料的 DSR 指南包括移轉服務

當客戶收到員工或其他資料主體的要求要執行權限，且該資料主體的個人資料在諮詢約定期間由 Microsoft 所收集，在此情況下如何接收 Microsoft 的協助。**

## <a name="microsoft-consulting-services"></a>Microsoft 諮詢服務

在套用 Microsoft 專業服務資料保護增補合約 (<https://aka.ms/professionalservicesdpa>) 之處簽署的 Microsoft 諮詢服務約定。

Microsoft 是與約定小組合作的客戶連絡人資料控制者。這些人員應連絡[隱私權回應中心](https://go.microsoft.com/fwlink/?LinkId=321116)以履行資料主體權限。

Microsoft 是在諮詢約定期間提供的資料內 DSR 的資料處理者。客戶應與約定經理連絡，以根據收集的資料以及提供的諮詢服務之特定類型，建立計畫來協助回應 DSR。若您的要求構成了通常出現在 Microsoft 諮詢服務約定內的工作層級，則可能需要額外的作業順序。此外，視諮詢約定類型而定，在時間範圍內的每次諮詢約定後會刪除個人資料。客戶可以要求更早刪除資料，並要求刪除證明。

## <a name="microsoft-fasttrack-services"></a>Microsoft FastTrack 服務

[Microsoft FastTrack](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Ffasttrack.microsoft.com%2Fabout&data=02%7C01%7C%7Cd0521d8739c841df674508d596834585%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636580412901207944&sdata=PO5eh56pm9IYk5Y%2Ff%2F31e%2BRVPmrC2Qi%2FCsw1NphR8gY%3D&reserved=0) 向組織提供 IT 諮詢服務，協助組織上線及使用 Microsoft 雲端服務，如 Microsoft 365、Azure 和 Dynamics 365。

Microsoft 是與 FastTrack 小組合作的客戶連絡人資料控制者。如果客戶連絡人希望存取、修改或移除 Microsoft FastTrack 記錄中的連絡人資訊，客戶可讓資料主體將要求直接傳送到 Office 365 FastTrack GDPR 要求收件匣中\<<o365ftgdpr@microsoft.com>\>。

對於 FastTrack 移轉服務而言，Microsoft 是資料處理者。根據我們的 FastTrack 額外隱私權揭露聲明，所有移轉中的資料都會被都視為「轉換資料」。如果您的組織忙於處理 FastTrack 移轉專案時，您需要執行 DSR，則必須特別謹慎。
  
如果使用者的資料正透過 FastTrack 移轉系統處理時，您需要處理任何存取權、修正或匯出 DSR 要求，客戶就有責任透過使用者資料儲存所在的現有來源系統來滿足這類 DSR。 一旦使用者的移轉完成且資料已移轉到目的地 Microsoft cloud 服務後，就會套用 Microsoft 針對客戶如何使用 Microsoft 產品、服務及系統管理工具來找出並處理個人資料，進而回應資料主體要求所提供的指引。 若要檢視此指引，請參閱 [GDPR 資料主體要求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests)。 

如果您的組織忙於處理進行中的 FastTrack 移轉專案時，您需要刪除使用者帳戶以回應 DSR 刪除要求，您應該知道移轉系統可能會在使用者完成移轉後，保留移轉資料複本一段時間，而刪除使用者帳戶並不會自動刪除 FastTrack 移轉系統中儲存的這類使用者移轉資料。如果您希望 Microsoft FastTrack 小組刪除使用者移轉資料，您可以[提交要求](https://go.microsoft.com/fwlink/?linkid=874544)。在一般商務過程中，Microsoft FastTrack 會在貴組織的移轉完成後，刪除所有的資料複本。

## <a name="other-consulting-services"></a>其他諮詢服務

透過 Microsoft 接收其他專業服務的客戶，應透過約定小組達成所有 GDPR 要求。如果約定小組無法提供履行 GDPR DSR 的清楚指示，客戶可以連絡[隱私權回應中心](https://go.microsoft.com/fwlink/?LinkId=321116)以取得協助。
