---
title: 一般資料保護規定
description: 一般資料保護規定 (GDPR) 的 Microsoft 技術指導
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: d64d9b98fe3cf24a14b3f3126ff3f38b1d84087d
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2020
ms.locfileid: "41557980"
---
# <a name="general-data-protection-regulation-summary"></a>一般資料保護摘要

針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處都必須遵守。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrOQI] 

這份文件將引導您在使用 Microsoft 產品和服務時，幫助取得 GDPR 規定下執行權限和完成義務的資訊。 [GDPR 的建議動作方案](gdpr-action-plan.md)與[責任整備檢查清單](gdpr-arc.md)提供評估及實作GDPR 合規性的其他資源。

## <a name="terminology"></a>術語

本文件中使用的 GDPR 術語的實用定義：

- 資料控制者 (控制者)**：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。  
- 個人資料** 和資料主體**：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。  
- 處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。  
- *客戶資料*：在公司運作的日常作業中產生並儲存的資料。

## <a name="what-is-the-gdpr"></a>GDPR 是什麼？

GDPR 提供人員管理組織中收集之個人資料的權限。 透過資料主體要求 (DSR) 使用這些權限。 組織必須提供關於 DSR 和資料外洩，以及執行資料保護影響評估 (DPIA) 的即時資訊。

實作或評估 GDPR 需求時，應考慮幾點。

- 開發或評估您 GDPR 合規性資料的隱私權原則。
- 評估貴組織的資料安全性。
- 誰是您的資料控制者？
- 可能有哪些必須執行的資料安全性處理程序？

[GDPR 的建議動作方案](gdpr-action-plan.md)與[責任整備檢查清單](gdpr-arc.md)可能會提示其他思考重點。

以下任務與達成 GDPR 標準相關。 請跟隨清單中的連結來取得有關實作的詳細資料。  

- **[資料主體要求 (DSR)](gdpr-data-subject-requests.md)**。 由資料主體向控制者提出以對其個人資料採取行動 (變更、限制、存取) 的正式要求。
- **[外洩通知](gdpr-breach-notification.md)**。 在 GDPR 規範下，個人資料外洩是「導致意外或非法損毀、遺失、變更、未經授權洩漏或存取所傳輸、儲存或處理的個人資料之安全性缺口。」
- **[資料保護影響評估](gdpr-data-protection-impact-assessments.md)**。 GDPR 規定資料控制者為「可能導致自然人之權利和自由高風險」的資料作業準備資料保護影響評估 (DPIA)。

如上所述，GDPR 的建議動作方案和責任整備檢查清單提供使用 Microsoft 產品和服務時，實作或評估 GDPR 合規性的指南。

## <a name="the-gdpr-in-action"></a>GDPR 實際運作方式

本節提供完成上述 GDPR 任務的大綱和思考重點。 完成這些工作可能會根據您的 Microsoft 設定而有所不同。

### <a name="data-subject-request-dsr"></a>資料主體要求 (DSR)

資料主體要求為資料主體提供執行 GDPR 規範下權限的方式。 控制者會負責提供即時且 GDPR 合規性的回覆。 您應該考慮解決以下問題。 如需技術詳細資訊，請參閱[資料主體要求](gdpr-data-subject-requests.md)。  

- **完成 DSR需要何種動作？**：DSRs 包含六種動作：探索、存取、改正、限制、匯出和刪除。
- **資料來源為何？**：大部分的組織資料在 [Office 應用程式](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)中產生，例如 Excel 和 Outlook。 您還可以在 Microsoft 產品和服務產生的[深入解析](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)和[系統產生的記錄](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)中找到 DSR 相關資料。
- **需要搜尋何種資料？**：個人資料可能會出現在客戶資料，Microsoft 產品和服務產生的深入解析，以及系統產生的記錄中。
- **如何搜尋個人資料？**：搜尋的個人資料可能會因 Microsoft 產品和服務而有所不同。 搜尋工具包含[內容搜尋](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)，或[應用程式內搜尋](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs)容量。 系統管理員可以存取使用者活動相關聯之[系統產生的記錄](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)。  
- **個人資料該以何種格式呈現？**：GDPR「資料可攜帶權」允許資料主體以「經過結構化、常用的、機器可讀取的格式」，要求其個人資料的複本，以及要求貴組織將這些檔案傳輸給另一個資料控制者。

### <a name="data-protection-impact-assessment"></a>資料保護影響評估

GDPR 規範下，資料控制者需要為「可能導致自然人之權利和自由高風險」的處理作業準備[資料保護影響評估](gdpr-data-protection-impact-assessments.md) (DPIA)。 Microsoft 產品和服務中沒有需要 DPIA 建立的項目。 而是取決於您 Microsoft 設定的詳細資料。

以下為一些考量 DPIA 相關的一些考量。 [DPIA 內容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)中可找到 Office 中必須考量的詳細資訊清單。

- 貴組織中的何種資料活動可能會危害您的個人資料安全？
- 您的 Microsoft 產品和服務設定可能造成易受資料外洩的攻擊嗎？
- 何時必須進行 DPIA？

    - 控制者需要執行 DPIA 來解決個人資料安全風險，或因資料外洩而造成的風險。 Office 中特定風險因素的範例可在[判斷是否需要 DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed)中得到解決。  

- 完成 DPIA 的必要項目？

    GDPR 強制需要 DPIA 的包含項目：  
    - 評估與 DPIA 目的相關之資料處理的必要性和相稱性。
    - 評估資料主體的權利和自由風險。
    - 意圖解決風險的措施、防護措施、安全性措施，和確保個人資料保護並證明遵守 GDPR 的機制。

### <a name="breach-notification"></a>外洩通知

身為資料處理者，Microsoft 確保客戶能夠符合 GDPR 外洩通知需求。 資料控制者負責評估資料隱私權的風險，並且決定外洩時是否需要客戶 DPA 的通知。 Microsoft 提供進行該評估所需的資訊。 如需 Microsoft 如何偵測及回應個人資料外洩的詳細資訊，請參閱 [GDPR 規定的資料外泄通知](gdpr-breach-notification.md)。 部分外洩通知問題是：

- 何種外洩相關資訊應該傳達給資料主體
- 如何與資料主體通訊 (電子郵件、書寫通知等)？

### <a name="accountability-readiness-checklists-for-the-gdpr"></a>符合 GDPR 的責任整備檢查清單

這些[檢查清單](gdpr-arc.md) 提供使用 Microsoft 產品時，便於存取支援 GDPR 所需資訊的方式。 您可以使用 [Microsoft 合規性管分數](compliance-score.md)管理檢查清單項目，方法是參考 GDPR 動態磚中 [客戶管理控制措施] 底下的控制措施識別碼和控制措施標題。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
