---
title: 符合 GDPR 的責任整備檢查清單
description: 在本文中，您將了解有關責任整備檢查清單使用 Microsoft 產品與服務時，以存取支援 GDPR 所需資訊。
keywords: Microsoft 365、Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 6952545060a524ef92af6e1e7a063da7091b0860
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214808"
---
# <a name="support-your-gdpr-program-with-accountability-readiness-checklists"></a>使用責任整備檢查清單支援 GDPR 計劃

針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處都必須遵守。 [GDPR 摘要主題](gdpr.md)中有其他詳細資料。

## <a name="accountability-readiness-checklists"></a>責任整備檢查清單

責任整備檢查清單提供使用 Microsoft 產品與服務時，便於存取支援 GDPR 所需資訊的方式。 檢查清單列出在 GDPR 下您可能須盡的義務，並指出支援貴組織的法規遵循所需的資訊。

四項 Microsoft 產品和服務系列的特定指南：

- [Office 365](gdpr-arc-Office365.md)
- [Dynamics 365](gdpr-arc-Dynamics365.md)
- [Azure](gdpr-arc-Azure.md)
- [Microsoft 支援服務與專業服務](gdpr-arc-prof-services.md)

您可以使用[「合規性管理員」](compliance-manager.md)管理此檢查清單中的項目，方法是參考 GDPR 圖格中「客戶受管理控制項」底下的控制項識別碼和控制項標題。

檢查清單包含以下列出之支援 GDPR 隱私計劃的四項基本考量類別，以及範例需求。

1. 資料收集和處理的條件：

    - 何時取得同意？  
    - 確定並記錄目的  
    - 隱私權影響評估

2. 資料主體權利  

    - 判斷屬於 PII 主體 (資料主體) 的資訊  
    - 提供可修改或撤銷同意的機制

3. 從設計著手保護隱私與預設為保護隱私  

    - 限制收集  
    - 遵守識別層級  
    - 暫存檔

4. 資料保護和安全性  

    - 了解組織和其內容  
    - 規劃  
    - 資訊安全性原則

## <a name="customer-agreements"></a>客戶合約

- **線上服務條款**：您可以在[線上服務條款](https://go.microsoft.com/fwlink/p/?linkid=2052208)中找到與 GDPR 相關的 Microsoft 合約承諾。
- **Microsoft 產品條款**：Microsoft 將 [GDPR 條款承諾](https://go.microsoft.com/fwlink/p/?linkid=2052213)擴展至所有大量授權客戶。
- **資料保護附錄**：Microsoft 服務[將承諾擴展](https://go.microsoft.com/fwlink/p/?linkid=2052215)至 Microsoft 諮詢服務客戶及其他人。

## <a name="gdpr-compliance-controls"></a>GDPR 合規性控制

- **使用合規性管理員**：審閱和整合 Microsoft 用來支援 GDPR 中的義務與[合規性管理員](compliance-manager.md)的控制。
- **GDPR 控制對應**：存取 Microsoft 控制的[完整對應](https://go.microsoft.com/fwlink/p/?linkid=2052220) ，以盡 GDPR 義務。

## <a name="records-of-processing-for-processors"></a>處理器的處理記錄

由於我們作為處理者向控制者客戶提供線上服務的規模和廣度，我們希望客戶能夠識別它們尋找處理記錄的服務，並在我們提供的線上工具中檢索相關記錄。 其中一個範例是關於 Azure 的處理記錄，其中客戶會被要求識別他們搜尋記錄的處理活動類型。

### <a name="azure-logs"></a>Azure 記錄

通常，客戶對活動記錄及診斷記錄感興趣：

- **活動記錄**： [活動記錄](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) 提供對訂閱中資源執行的操作的深入了解。 活動記錄可協助您判斷作業的發起者、發生時間和狀態。
- **診斷記錄**：[診斷記錄](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) 是由每個資源產生的所有記錄。 這些記錄包括 Windows 事件系統記錄、Azure 儲存空間記錄、Key Vault 稽核記錄，以及應用程式閘道存取和防火牆記錄。
- **記錄封存**：所有診斷記錄都會寫入集中式加密的 Azure 儲存空間帳戶以封存。 保留期是使用者可設定的，最多 730 天，以滿足特定於組織的保留要求。 這些記錄連線到 Azure 監視器記錄，以進行處理、儲存及儀表板報告。

### <a name="other-logs"></a>其他紀錄

此外，以下監視解決方案已作為此結構的一部分安裝。 客戶有責任設定這些解決方案，使其與FedRAMP 安全性控制保持一致：

- [AD 評估](https://docs.microsoft.com/azure/azure-monitor/insights/ad-assessment)：Active Directory 健康情況檢查解決方案定期評估服務器環境的風險和健康狀況，並提供特定於已設定服務器基礎結構的建議的優先順序清單。
- [反惡意程式碼評估](https://docs.microsoft.com/azure/security-center/security-center-services?tabs=features-windows#supported-endpoint-protection-solutions-)：[反惡意程式碼] 解決方案報告惡意軟體、威脅和保護狀態。
- [Azure 自動化](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker)： [Azure 自動化] 解決方案儲存、執行和管理 Runbook。
- [安全性與稽核](https://docs.microsoft.com/azure/security-center/security-center-introduction)：[安全性與稽核] 儀錶板通過提供有關安全性網域、顯著問題、偵測、威脅情報和常見安全査詢的計量，提供對資源安全狀態的高級深入解析。
- [SQL 評估](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment)：[SQL 健康情況檢查] 解決方案定期評估服務器環境的風險和健康狀況，並提供特定於已設定服務器基礎結構的建議的優先順序清單。
- [更新管理](https://docs.microsoft.com/azure/automation/update-management/update-mgmt-overview)：[更新管理] 解決方案允許客戶管理作業系統安全性更新，包括可用更新的狀態和安裝所需更新的程式。
- [代理程式健康情況](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)：[代理程式健康情況] 決方案會報告設定多少個代理及其地理分配、有多少個無回應代理、和正在提交可執行資料的代理數目。
- [Azure 活動記錄](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log)：[活動紀錄分析] 解決方案協助分析客戶的所有 Azure 訂閱的 Azure 活動紀錄。
- [變更追蹤](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log)：[變更追蹤] 解決方案可讓客戶輕鬆識別環境中變更。

有關 Azure 技術與安全性措施的資訊，控制者客戶應造訪[Azure 全性文件](https://docs.microsoft.com/azure/security/)。 由於 Microsoft 不知道客戶資料是否是個人資料，所以 Azure 處理所有客戶資料就像處理個人資料一樣，因此客戶可能會認為所有的資料都是相關的。

### <a name="processor-information"></a>處理者資訊

另一個客戶可能需要處理者處理資訊記錄的產品是 Office 365。 若要查看與 Office 365 相關的資訊，請參閱 [在安全性與合規性中心中搜尋稽核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)一文。

您也可以使用安全性與合規性中心查看Dynamics 365 的資訊。  若要查看安全性與合規性中心頁面，請確保您具有正確的授權。 通過[安全性與合規性中心服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)文章了解有關授權的更多資訊。 要搜尋 Dynamics 365 事件，請訪問[安全性與合規性中心](https://protection.office.com/unifiedauditlog)中的整合稽核記錄。

### <a name="professional-services-information"></a>專業服務資訊

對於專業服務，專業服務支援資料由客戶代表提供給支援工程師。  當客戶通過線上產品入口網站、服務中心或電話提交服務要求時，可能會發生這種情況。

該資訊會儲存在我們的 CRM 系統中，且僅用於以下目的：

- 提供專業服務，包括提供技術支援、專業規劃、建議、指導方針、資料遷移、設定和解決方案/軟體發展服務。  
- 疑難排解 (預防、偵測、調查、緩解和修復問題，包括安全性事件)；以及 
- 持續改進 (維護專業服務，包括安裝最新更新，改進可靠性、有效性、品質和安全性)。 

由於我們支持作業規模，Microsoft 運營產品組型的 CRM 系統。 處理記錄將包含在這些系統中。
處理歷史記錄反映在我們的 CRM 系統中保存的記錄中。  在大多數情况下，服務要求歷史記錄在入口網站或服務中心上可用。
如需入口網站上沒有的特定詳細資料、或其他任何有關資料處理的查詢，請與您的技術客戶經理或與 [Microsoft 技術支援](https://support.microsoft.com/contactus/) 連絡。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
