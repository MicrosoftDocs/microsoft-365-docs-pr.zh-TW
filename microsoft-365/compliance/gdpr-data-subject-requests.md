---
title: GDPR 和 CCPA 的資料主體要求
description: ''
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
titleSuffix: Microsoft GDPR
ms.openlocfilehash: fc5f4f8752d17595cfafaa39626f0d36675d7c82
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558053"
---
# <a name="data-subject-requests-and-the-gdpr-and-ccpa"></a>GDPR 與 CCPA 和資料主體要求

針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處都必須遵守。 您可以在 [GDPR 摘要主題](gdpr.md)中找到其他詳細資料。

同樣地，加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。  CCPA 也提供特定接露、針對選擇行使權時的歧視提供保護，以及特定資料傳輸的「選擇退出/選擇加入」需求分類為「銷售」。 本文件會引導您了解依據 GDPR 和 CCPA 使用 Microsoft 產品和服務時，完成資料主體要求 (DSR) 的相關資訊。

- [Office 365](gdpr-dsr-Office365.md)
- [Azure](gdpr-dsr-Azure.md)
- [Intune](gdpr-dsr-Intune.md)
- [Dynamics 365](gdpr-dsr-Dynamics365.md)
- [Visual Studio 系列](gdpr-dsr-visual-studio-family.md)
- [Azure DevOps Services](gdpr-dsr-vsts.md)
- [Microsoft 支援服務與專業服務](gdpr-dsr-prof-services.md)

## <a name="terminology"></a>術語

本文件中使用的 GDPR 術語的實用定義：

- 資料控制者 (控制者)**：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。  
- 個人資料** 和資料主體**：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。  
- 處理者：** 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。  
- *客戶資料：* 在公司運作的日常作業中產生並儲存的資料。

## <a name="what-is-a-dsr"></a>什麼是 DSR？

一般資料保護規定 (GDPR) 賦予人們 (在此法規中稱為資料主體) 權利來管理雇主或其他類型的代理機構或組織 (稱為資料控制者或僅稱為控制者) 所收集的個人資料。 GDPR 為資料主體提供其個人資料的特定權限；這些權限包括取得個人資料副本、要求對該資料的變更、限制對該資料的處理、刪除該資料，或是以電子格式接收該資料以移至另一個控制者。

加州消費者隱私法 (CCPA) 為加州客戶提供隱私權和義務，包括與 GDPR 資料主體權利相似的權利，例如有權刪除、存取和接收 (可攜性) 其個人資訊。  

身為控制者的您，有義務盡快考慮每項 DSR，並採取要求的動作來提供實質回應，或針對控制者無法滿足 DSR 的原因進行說明。 控制者應向其法律或法務遵循顧問諮詢有關適當處置任何特定 DSR 的方法。

受限於組織的 GDPR 符合性規則，完成 DSR 可能涉及數個程序。
  
- **探索**。 決定需要什麼資料才能完成 DSR 的程序。
- **存取**。 擷取並可能傳輸給所發現資訊的資料主體。
- **修正**。 實作變更或其他要求的個人資料變更。
- **限制**。 利用限制存取或從 Microsoft 雲端中移除資料來變更存取或個人資料的處理。
- **匯出**。 對資料主體提供「結構化、常用、機器可讀取格式」的個人資料，如 GDPR 的「資料可攜帶權」所提供。
- **刪除**。 從 Microsoft 雲端永久移除個人資料。

## <a name="specific-dsr-considerations"></a>指定 DSR 考量

### <a name="insights-generated-by-microsoft-products-or-services"></a>Microsoft 產品或服務產生的深入資訊

[深入資訊](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)可能由服務 (MyAnalytics 等) 產生。Office 365 包含的線上服務可為其使用其服務的使用者和組織提供深入資訊。 這些服務所產生的資料可能會產生與 DSR 相關的個人資料。 請遵循下列連結來取得有關特定服務 DSR 程序的詳細資料。  

### <a name="dsrs-for-system-generated-logs"></a>系統產生的記錄檔的 DSR

Microsoft 產生的記錄檔和相關資料可能包含依據 GDPR 的「個人資料」定義，被視為個人的資料。 不支援限制或修正系統產生的記錄檔中的資料。 系統產生的記錄檔中的資料構成了 Microsoft 雲端內所進行的實際動作和診斷資料，修改會危害動作的歷程記錄，並增加詐騙和安全性風險。 Microsoft 提供存取、匯出和刪除系統產生的記錄檔的功能，這些記錄檔可能是完成 DSR 所需。 這類資料的範例可能包括：  

- 產品和服務使用情況資料 (例如使用者活動記錄)
- 使用者搜尋要求和查詢資料
- 產品和服務透過系統功能和使用者或其他系統的互動產生的資料。  

### <a name="yammer-and-kaizala"></a>Yammer 和 Kaizala

刪除使用者帳戶不會移除系統為 Yammer 和 Kaizala 所產生的記錄。若要從這些應用程式中移除資料，請參閱以下其中一個資源：

- [管理 Yammer Enterprise 中的 GDPR 資料主體要求](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [在 Kaizala 中匯出或刪除使用者的組織資料](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a>國家/地區雲端

在某些國家/地區的雲端中，全域 IT 系統管理員必須刪除由系統產生的記錄檔。

### <a name="microsoft-services"></a>Microsoft 服務

如果您的組織或使用者與 Microsoft 交涉以接收與 Microsoft 產品和服務相關的支援，則此資料中的一部分可能包含個人資料。 如需詳細資訊，請參閱 [GDPR 的 Microsoft 支援服務與專業服務資料主體要求](gdpr-dsr-prof-services.md)。

### <a name="microsoft-controller-products"></a>Microsoft 控制者產品

在某些情況下，組織的使用者可以存取 Microsoft 為資料控制者的 Microsoft 產品或服務。 在這些情況下，使用者必須直接向 Microsoft 起始自己的 DSR，而 Microsoft 會直接向使用者履行要求。

### <a name="third-party-products"></a>協力廠商產品

針對透過 Microsoft 帳戶驗證存取的協力廠商產品和服務，應該將任何資料主體要求導向至適當的協力廠商。

## <a name="data-subject-request-admin-tools"></a>資料主體要求系統管理工具

- **安全性與合規性中心**：使用者產生的資料是由[安全性與合規性中心](https://aka.ms/stpsecurityandcompliance)匯出，或以應用程式功能匯出。
- **Azure AD 系統管理中心**：使用 [Azure AD 系統管理中心](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/)刪除來自 Azure Active Directory 及相關服務的資料主體。
- **Microsoft 資料記錄匯出**：租用戶系統管理員可以使用 [Microsoft 資料記錄匯出](https://aka.ms/MicrosoftGDPR)，將系統產生的記錄匯出。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
