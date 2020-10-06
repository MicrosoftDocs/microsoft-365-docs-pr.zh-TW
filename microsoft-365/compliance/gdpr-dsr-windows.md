---
title: 適用於 GDPR 和 CCPA 的 Windows 企業版資料主體要求的資料處理者服務
description: 了解如何使用 Microsoft 產品、服務及系統管理工具，尋找並處理個人資料以回應 DSR 要求。
keywords: Microsoft 365、Microsoft 365 教育版, Microsoft 365 文件, GDPR
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
ms.openlocfilehash: 916ee45dae92d14c78b92bb16b6dca7c455bf803
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304897"
---
# <a name="data-processor-service-for-windows-enterprise-data-subject-requests-for-the-gdpr-and-ccpa"></a>適用於 GDPR 和 CCPA 的 Windows 企業版資料主體要求的資料處理者服務 

>[!NOTE]
>本主題適用於 Windows 企業版預覽計畫的資料處理者服務中的參與者，且需要接受特定使用條款。 若要深入了解該計畫並同意使用條款，請參閱 [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview)。

## <a name="introduction-to-data-subject-requests-dsrs"></a>資料主體要求 (DSR) 簡介 
歐盟一般資料保護規定 (GDPR) 賦予人們 (在此法規中稱為_資料主體_) 權利來管理雇主或其他類型的代理機構或組織 (稱為_資料控制者_或僅稱為_控制者_) 所收集的個人資料。 依據 GDPR，個人資料的定義很廣泛，舉凡與已識別或可識別自然人相關的任何資料皆屬之。 GDPR 為資料主體提供其個人資料的特定權限；這些權限包括取得個人資料副本、要求對該資料進行更正、限制對該資料的處理、刪除該資料，或是以電子格式接收該資料以移至另一個控制者。 由資料主體向控制者提出以對其個人資料採取行動的正式要求，稱為_資料主體要求_或 DSR。 

同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。 CCPA 也提供特定接露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。 銷售的廣泛定義，包括出於有價值的考量而共用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa)和[常見問題集](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq)。

本指南會討論如何使用 Microsoft 產品、服務及系統管理工具，協助我們的控制者客戶找出並對個人資料採取動作，以回應 DSR；尤其是針對如何找出、存取與處理在 Microsoft 雲端中常駐的個人資料。以下是本指南中所述程序的快速概觀： 

1. **存取**—擷取在 Microsoft 雲端中常駐的個人資料，若有要求，請製作可供資料主體使用的副本。 
2. **刪除**—將會永久移除 Microsoft 雲端中常駐的個人資料。 
3. **匯出**—將個人資料的電子副本 (以機器可讀取的格式) 提供給資料主體。 CCPA 中的個人資訊是任何與已識別或可識別個人相關的資訊。

CCPA 中的個人資訊是任何與已識別或可識別個人相關的資訊。 個人的私人、公開或公司角色之間沒有區別。 定義的「個人資訊」一詞大致與 GDPR 下的「個人資料」對應。 不過，CCPA 也包含家庭和家用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa)和[常見問題集](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq)。

本指南中的每一節說明資料控制者組織可以採取的程序，以回應對 Microsoft 雲端中個人資料的 DSR。 

## <a name="terminology"></a>術語

以下清單提供與本指南相關的詞彙定義。 

* _控制者_：自然人或法人、公家機關、局處或其他機構，不論單獨或與其他單位聯合，會決定處理個人資料的用途以及方式，其中此類處理的用途以及方式的判斷是根據聯盟與成員國法律，控制者人選或提名控制者的特定準則可由聯盟與成員國法律提供。 

* _個人資料和資料主體_：表示與已識別或可識別之自然人 (以下稱為「資料主體」) 相關的任何資訊；可識別的自然人是可以直接或間接識別的人員，尤其是藉由參照如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身分等一個或多個識別碼來識別。 

* _處理者_：代表控制者處理個人資料的自然人或法人、公務機關、局處或其他機構。 

* _客戶資料_：由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。 

* _Windows 診斷資料_：來自 Windows 裝置的重要技術資料，那些資料和裝置以及 Windows 與相關軟體的執行狀況有關。 這是用來讓 Windows 保持最新、安全、可靠、性能，並透過對 Windows 使用狀況進行綜合分析來改善 Windows。 Windows 診斷資料的一些範例是使用的硬體類型、按其各自用途安裝的應用程式以及裝置驅動程式上的可靠性資訊。 某些 Windows 元件及應用程式會直接連線到 Microsoft 服務，但是它們交換的資料並非 Windows 診斷資料。 例如，交換使用者位置以取得當地的天氣或新聞，並不是 Windows 診斷資料的範例。 

## <a name="how-to-use-this-guide"></a>如何使用本指南 

當您在 Windows 企業版註冊裝置使用資料處理者服務時，Windows 會產生一些稱為 Windows 診斷資料的資訊，以便提供服務。

## <a name="windows-diagnostic-data"></a>Windows 診斷資料 

Microsoft 提供功能，讓您存取、刪除及匯出與使用者使用 Windows 企業版資料處理者服務相關的 Windows 診斷資料。

>[!IMPORTANT]
>不支援修正 Windows 診斷資料的功能。 Windows 診斷資料構成了 Windows 中所進行的實際動作，對這類資料的修改會危害動作的歷程記錄，並增加安全性風險並危害可靠性。 本文件涵蓋的所有資料都視為 Windows 診斷資料。 

## <a name="executing-dsrs-against-windows-diagnostic-data"></a>針對 Windows 診斷資料執行 DSR 

Microsoft 透過 Azure 入口網站以及直接透過現有的應用程式開發介面 (API)，提供了存取、刪除及匯出特定 Windows 診斷資料的功能。

### <a name="step-1-access"></a>步驟 1：存取 

租用戶系統管理員是組織中唯一能夠存取 Windows 診斷資料的人，該資料與特定使用者對 Windows 企業版註冊裝置的資料處理者服務的使用狀況有關。 針對存取要求所擷取的資料會透過匯出，以機器可讀取的格式提供；且會以檔案的形式提供，讓使用者知道與資料相關聯的是哪些裝置與服務。 如上所述，所擷取的資料不會包含可能造成 Windows 裝置安全性或穩定性受損的資料。 

Microsoft 提供入口網站體驗，讓企業客戶的租用戶系統管理員能夠管理 DSR 存取要求。 [Azure DSR，第 2 部分，步驟 3：匯出](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export)說明如何透過匯出在 Azure 入口網站中執行 DSR 存取要求。

### <a name="step-2-delete"></a>步驟 2：刪除 

Microsoft 提供了一種根據特定使用者的 Azure Active Directory 物件，執行基於使用者的 DSR 刪除要求的方法。

針對基於使用者的刪除要求，Microsoft 提供入口網站，讓企業客戶的租用戶系統管理員能夠管理 DSR 刪除要求。 [Azure DSR，第 1 部分，步驟 5：刪除](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-5-delete)說明如何透過 Azure 入口網站執行 DSR 刪除要求。 

Microsoft 能夠直接透過現有的應用程式開發介面 (API) 刪除使用者，進而刪除客戶資料。 詳細資料請參閱 [API 參考文件](https://docs.microsoft.com/graph/api/directory-deleteditems-delete?view=graph-rest-beta)。 

>[!IMPORTANT]  
>刪除收集的資料並不會停止日後的收集。 若要關閉資料收集，請按照[各自服務的參考文件](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)中所述的程序。
 
 此外，基於使用者的刪除要求也需要刪除使用者本身的帳戶。 

### <a name="step-3-export"></a>步驟 3：匯出 

租用戶系統管理員是組織中唯一能夠存取 Windows 診斷資料的人，該資料與特定使用者對 Windows 企業版註冊裝置的資料處理者服務的使用狀況有關。 針對匯出要求所擷取的資料會以機器可讀取的格式提供；且會以檔案的形式提供，讓使用者知道與資料相關聯的是哪些裝置與服務。 如上所述，所擷取的資料不會包含可能造成 Windows 裝置安全性或穩定性受損的資料。 [Azure DSR，第 2 部分，步驟 3：匯出](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export)說明如何透過 Azure 入口網站執行 DSR 匯出要求。 

Microsoft 能夠直接透過現有的應用程式開發介面 (API) 匯出客戶資料。 詳細資料請參閱 [API 參考文件](https://docs.microsoft.com/graph/api/user-exportpersonaldata?view=graph-rest-1.0)。

## <a name="notify-about-exporting-or-deleting-issues"></a>匯出或刪除問題的通知 

如果您從 Azure 入口網站匯出或刪除資料時遇到問題，請前往 Azure 入口網站 [協助 + 支援]**** 刀鋒視窗，並在 [訂閱管理 > 其他安全性和法規遵循要求> 隱私權刀鋒視窗和 GDPR 要求]**** 下提交新票證。 
