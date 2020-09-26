---
title: 服務組織控制 (SOC)
description: Microsoft 雲端服務符合服務組織控制的作業安全性標準。
keywords: Microsoft 365, 合規性, 方案
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: a648673d06300190695db52d14e85f114bfe0e87
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208143"
---
# <a name="service-organization-controls-soc"></a>服務組織控制 (SOC)

## <a name="soc-1-2-and-3-reports-overview"></a>SOC 1、2 和 3 報告概觀

越來越多企業將基本功能 (例如資料儲存空間和應用程式存取權) 外包給雲端服務提供者 (CSP) 和其他服務組織。 對此，美國會計師協會 (AICPA) 開發了服務組織控制 (SOC) 架構，這是一種可保護在雲端儲存及處理的資訊機密性和隱私權的控制標準。 這與國際服務組織的報告標準《國際鑑證業務準則》(ISAE) 相符。

以 SOC 架構為基礎的服務稽核分為兩個類別：SOC 1 和 SOC 2，適用於範圍內的 Microsoft 雲端服務。

SOC 1 稽核 (適用於稽核財務報表的 CPA 公司) 評估影響使用提供者雲端服務的客戶財務報告的 CSP 內部控制效能。 《簽證服務準則公報第18 號》(SSAE 18) 和《國際鑑證業務準則第 3402 號》 (ISAE 3402) 是執行稽核的標準，而且是 SOC 1 報告的基礎。

SOC 2 稽核根據 AICPA 信任服務原則和標準來計量 CSP 系統的效能。 簽證準則 (AT) 第 101 節中的簽證服務是 SOC 2 和 SOC 3 報告的基礎。

在 SOC 1 或 SOC 2 稽核結束時，服務稽核員會在 SOC 1 Type 2 或 SOC 2 Type 2 報告中提出意見，其中描述 CSP 的系統，並評估 CSP 對其控制項的描述是否公平。 並且評估 CSP 的控制項是否適當設計、是否已在指定日期執行，且在指定的期間內有效運作。

稽核員也可建立 SOC 3 報告 (SOC 2 Type 2 稽核報告的簡化版)，該報告適用於想要保證 CSP 控制項但不需要完整 SOC 2 報告的使用者。 只有當 CSP 的 SOC 2 稽核意見不合格時，才能授予 SOC 3 報告。

## <a name="microsoft-and-soc-1-2-and-3-reports"></a>Microsoft 和 SOC 1、SOC 2 和 SOC 3 報告

獨立協力廠商稽核員會根據 SOC 報告架構對 Microsoft 涵蓋的雲端服務進行稽核，至少一年一次。 Microsoft 雲端服務的稽核涵蓋關於資料安全性、可用性、處理完整性和機密性等控制項 (如果每個服務的範圍內信任原則適用)。

Microsoft 已取得 SOC 1 Type 2、SOC 2 Type 2 和 SOC 3 報告。 通常，SOC 1 和 SOC 2 報告僅提供與 Microsoft 簽署保密協議的客戶使用；SOC 3 報告則提供公開使用。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

### <a name="covered-services-for-soc-1-and-soc-2"></a>SOC 1 和 SOC 2 涵蓋的服務

- [Azure、Azure Government 和 Azure 德國](https://aka.ms/AzureCompliance)
- Microsoft Cloud App Security
- [Dynamics 365 和 Dynamics 365 美國政府](https://aka.ms/d365-compliance-list)
- Microsoft Graph
- Intune
- Microsoft 受管理的電腦
- Power Automate (先前為 Microsoft Flow) 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中
- [Office 365、Office 365 美國政府和 Office 365 美國政府國防版](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- PowerApps 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中
- Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中
- Microsoft Stream
- Azure DevOps Services

### <a name="covered-services-for-soc-3"></a>SOC 3 涵蓋的服務

- [Azure、Azure Government 和 Azure 德國](https://aka.ms/AzureCompliance)
- Microsoft Cloud App Security
- Microsoft Graph
- Intune
- Microsoft 受管理的電腦
- Power Automate (先前為 Microsoft Flow) 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中
- PowerApps 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中
- [Office 365、Office 365 美國政府和 Office 365 美國政府國防版](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Power BI
- Microsoft Stream

## <a name="audits-reports-and-certificates"></a>稽核、報告和憑證

### <a name="audit-cycle"></a>稽核週期

Microsoft 雲端服務針對 SOC 1 (SSAE18，ISAE 3402)、SOC 2 (AT 第 101 節) 和 SOC 3 標準，至少一年稽核一次。

#### <a name="azure-dynamics-365-microsoft-cloud-app-security-flow-microsoft-graph-intune-power-bi-powerapps-microsoft-stream-and-microsoft-datacenters"></a>Azure、Dynamics 365、Microsoft Cloud App Security、Flow、Microsoft Graph、Intune、Power BI、PowerApps、Microsoft Stream 和 Microsoft 資料中心

- [Azure + Dynamics 365 及 Azure + Dynamics 365 Government SOC 1 Type 2 報告](https://aka.ms/azuresoc1auditreport)
- [Azure + Dynamics 365 及 Azure + Dynamics 365 Government SOC 2 Type 2 報告](https://aka.ms/azuresoc2auditreport)
- [Azure + Dynamics 365 及 Azure + Dynamics 365 Government SOC 3 報告](https://aka.ms/azuresoc3auditreport)

#### <a name="office-365"></a>Office 365

- [Office 365 核心版 - SSAE 18 SOC 1 報告](https://aka.ms/o365SOC-1)
- [Office 365 核心版 - SSAE 18 SOC 2 報告](https://aka.ms/o365SOC-2)
- [Office 365 核心版 - SSAE 18 SOC 3 報告](https://aka.ms/o365SOC-3)
- [Office 365 微服務 T1-SSAE 18 SOC2 Type I 報告](https://aka.ms/o365-MS-SOC-2-type1)
- [客戶加密箱 SOC 1 SSAE 16 稽核報告](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [Yammer SOC 2 AT 101 Type I 稽核報告](https://aka.ms/YammerSOC2Type1AuditReport)
- [Yammer SOC 2 Type II 報告](https://aka.ms/yammerSOC-2)
- [請參閱 Bridge Letter 和其他稽核報告](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a>常見問題集

**如何取得 SOC 報告的複本？**

您的稽核員可以使用這些報告來比較 Microsoft 商務用雲端服務結果與您自己的法律和法規需求。

- 您可以透過[服務信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)查看所有 SOC 報告。
- 無法存取[服務信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)的 Azure DevOps 服務客戶可以向 [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) 傳送電子郵件，以取得其 SOC 1 和 SOC 2 報告。 此電子郵件僅用於要求 Azure DevOps SOC 報告。

**Azure SOC 報告多久發行一次？**

Azure、Microsoft Cloud App Security、Flow、Microsoft Graph、Intune、Power BI、PowerApps、Microsoft Stream 和 Microsoft 資料中心的 SOC 報告皆以 12 個月執行 (稽核期間) 為基礎，且每半年季發行新報告 (期間結束於 3 月 31 日與 9 月 30 日)。 每季都會發放銜接信件，以涵蓋前三個月的內容。 例如，1 月份的信件涵蓋10/1-12/31，4 月的信件涵蓋1/1-3/31，7 月的信件涵蓋4/1-6/30，而 10 月的信件則涵蓋7/1-9/30。 客戶可以從服務信任入口網站[下載](https://aka.ms/stp)最新報告。

**我是否需要自行執行 Microsoft 資料中心的稽核？**

否。 Microsoft 會與客戶共用獨立的稽核報告和認證，讓客戶能驗證 Microsoft 合規性及其安全性承諾。

**我是否可以在組織的憑證程序中使用 Microsoft 合規性？**

是。 當您將應用程式和資料移轉到涵蓋的 Microsoft 雲端服務時，您可以將 Microsoft 持有的稽核和認證作為建立基礎。 獨立報告可證明 Microsoft 實施用於維護資料安全性和隱私權的控制項效能。

**我要從何處著手組織自身的合規性工作？**

[適用於服務組織的 SOC 套件](https://aka.ms/soc-toolkit)是了解 SOC 報告程序及推動貴組織使用這些報告的實用資源。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>使用 Microsoft 合規性管理員來評估風險

[Microsoft 合規性管理員](compliance-manager.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的功能，可協助您了解組織的合規性狀況，並採取行動以協助降低風險。 合規性管理員會提供特優範本以為此法規建立評估。 可在合規性管理員的**評估範本**頁面尋找範本。 了解如何[在合規性管理員中建立評估](compliance-manager-assessments.md)。

## <a name="resources"></a>資源

- [使用 Microsoft 雲端服務，更進一步保護您的資料](https://www.microsoft.com/trustcenter/guidance/protect-data)
- [服務組織控制 (SOC) 報告](https://aka.ms/mssocreports)
- [SSAE 16 概觀](http://ssae16.com/SSAE16_overview.html)
- [ISAE 3402 概觀](http://isae3402.com/ISAE3402_overview.html)
- [Microsoft Online Services 條款](https://aka.ms/Online-Services-Terms)
- [Microsoft 政府雲端](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
