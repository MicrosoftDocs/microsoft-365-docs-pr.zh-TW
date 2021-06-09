---
title: 安全規範中心內的報告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: 使用安全性 & 合規性中心，取得 SharePoint 線上和 Exchange Online 組織的各種報告，以及 Azure Active Directory 報告。
ms.openlocfilehash: 3e72ecab68ece31c44d99f85806492e788f4cd7c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926151"
---
# <a name="reports-in-the-security--compliance-center"></a>安全規範中心內的報告

您可以使用 [安全性 & 規範中心] 中的 [**查看報告**] 頁面，快速存取 SharePoint 線上和 Exchange Online 組織的審計報告。 您也可以從 [**查看報告**] 頁面存取 Azure Active Directory (AD) 使用者登入報告、使用者活動報告和 Azure AD 審核記錄。 這是因為您付費的 Microsoft 365 訂閱包含 Microsoft Azure 的免費訂閱。 您第一次嘗試存取這些 Azure 報告時，您必須完成一次性註冊程式。 
  
> [!TIP]
> 若要查看組織中活動的其他報告，請參閱[Microsoft 365 系統管理中心的活動報告](../admin/activity-reports/activity-reports.md)。 
  
 **開始之前**
  
您必須具備下列許可權，才能在安全性 & 規範中心查看報告。
  
- 您必須在 Exchange 系統管理中心中指派 Security Reader 角色 (EAC) ，以查看安全性 & 規範中心內的報告。 根據預設，此角色會指派給 EAC 中的「組織管理」和「安全性讀者」角色群組。
    
- 您必須在 Security & 相容性中心內指派 View-Only DLP 合規性管理角色，才能在安全性 & 規範中心中查看 DLP 報告。 根據預設，此角色會指派給安全性 & 合規性中心內的合規性管理員、組織管理、安全性管理員及安全性讀者角色群組。

- 此外，您必須獲指派 EAC 中的 View-Only 收件者角色，才能在 EAC 中查看 DLP 報告。 根據預設，此角色會指派給 EAC 中的「規範管理」、「組織管理」和「View-Only 組織管理」角色群組。
  
 **若要在安全性 & 規範中心開啟「查看報告」頁面：**
  
1. 請移至 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。
    
2. 使用組織中使用者帳戶的認證登入。
    
在 [ **查看報告** ] 頁面上，您可以查看下列類型的報告： 
  
- [稽核報告](#auditing-reports)
- [主管審查報告](#supervisory-review-report)
- [資料外洩防護報告](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>稽核報告

下表說明安全性 & 規範中心的 [**查看報告**] 頁面上的 [**審計**] 區段中的報告。 
  
|**報告**|**描述**|
|:-----|:-----|
|**審核記錄報告** <br/> |您可以在組織中搜尋使用者和系統管理員活動的「審核記錄檔」。 報告包含 Exchange Online 中的使用者和系統管理員活動、SharePoint Online、商務用 OneDrive 和 Azure Active Directory，也就是 Office 365 的目錄服務。 如需詳細資訊，請參閱[搜尋 Office 365 中的「審核記錄](search-the-audit-log-in-security-and-compliance.md)」。  <br/> |
|**Azure AD 報告** <br/> |若要尋找組織中不尋常或可疑的登入活動，您可以在 Microsoft Azure 中使用登入和活動報告。 您也可以在 Azure AD 審核記錄中查看事件。 若要在 Azure 中查看報告，只要按一下 [ **查看 AZURE AD 報告**]。 如需詳細資訊，請參閱： <br/><br/>[在 Office 365 中使用免費的 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)。 <br/> [查看您的存取和使用方式報告](/azure/active-directory/reports-monitoring/overview-reports)。  <br/> |
|**Exchange 稽核報告** <br/> | 您可以使用 Microsoft 365 中的審計功能追蹤組織管理員對 Exchange Online 設定所做的變更。 也會記錄由 Microsoft 資料中心系統管理員或委派的系統管理員對 Exchange Online 組織所做的變更。 針對 Exchange Online，系統管理員審核記錄預設為啟用狀態，因此您不需要執行任何動作即可將其開啟。 Exchange Online 也提供信箱審核記錄，讓您追蹤信箱擁有者以外的人對信箱的存取權。 您必須針對您想要追蹤之非擁有者存取的每個信箱啟用信箱稽核記錄。  <br/>  對於系統管理員及信箱稽核記錄，您可以執行稽核報告，即可檢視稽核記錄項目。 您也可以匯出信箱和系統管理員稽核記錄，這些記錄會在 24 小時內，以 XML 檔案附加在電子郵件訊息中傳送給您。 <br/><br/>如需匯出稽核記錄的詳細資訊，請參閱：  <br/><br/> [匯出信箱稽核記錄](/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) <br/> [查看和匯出資料中心管理員審核記錄](/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) <br/> [搜尋角色群組變更或管理員稽核記錄檔](/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) <br/>   [Exchange 的審計報告](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)。  <br/> |
   
## <a name="supervisory-review-report"></a>主管審查報告

透過「主管審查」報告，您可以看到組織中所有主管審查原則的狀態。 如需詳細資訊，請參閱 [設定組織的主管審查原則](./communication-compliance-configure.md)。
  
## <a name="data-loss-prevention-reports"></a>資料外洩防護報告

資料遺失防護 (DLP) 報告包含的 DLP 原則及已套用至內容的規則相關資訊包含組織中的敏感性資料。 您也可以設定報告，即可顯示根據 DLP 原則和規則之動作的相關資訊。 如需詳細資訊，請參閱 [查看資料遺失防護報告](view-the-dlp-reports.md)。