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
description: '使用安全性 & 合規性中心，取得您 SharePoint 線上和 Exchange Online 組織的各種報告，以及 Azure Active Directory 報告。  '
ms.openlocfilehash: 9134cf403c8452ea457983226be04ba139bf72e6
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943282"
---
# <a name="reports-in-the-security--compliance-center"></a>安全規範中心內的報告

您可以使用 [安全性 & 規範中心] 中的 [**查看報告**] 頁面，快速存取 SharePoint Online 和 Exchange Online 組織的審計報告。 您也可以從 [**查看報告**] 頁面中，存取 Azure Active DIRECTORY （AD）使用者登入報告、使用者活動報告和 Azure AD 審核記錄。 這是因為您付費的 Microsoft 365 訂閱包含 Microsoft Azure 的免費訂閱。 您第一次嘗試存取這些 Azure 報告時，您必須完成一次性註冊程式。 
  
> [!TIP]
> 若要查看有關組織中活動的其他報告，請參閱[Microsoft 365 系統管理中心的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。 
  
 **開始之前**
  
您必須具備下列許可權，才能在安全性 & 規範中心查看報告。
  
- 您必須在 Exchange 系統管理中心（EAC）中指派 Security Reader 角色，才能在安全性 & 規範中心中查看報告。 根據預設，此角色會指派給 EAC 中的「組織管理」和「安全性讀者」角色群組。
    
- 您必須在 Security & 相容性中心內指派 View-Only DLP 合規性管理角色，才能在安全性 & 規範中心中查看 DLP 報告。 根據預設，此角色會指派給安全性 & 合規性中心內的合規性管理員、組織管理、安全性管理員及安全性讀者角色群組。

- 此外，您必須獲指派 EAC 中的 View-Only 收件者角色，才能在 EAC 中查看 DLP 報告。 根據預設，此角色會指派給 EAC 中的「規範管理」、「組織管理」和「View-Only 組織管理」角色群組。
  
 **若要在安全性 & 規範中心開啟「查看報告」頁面：**
  
1. 請移至 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。
    
2. 使用組織中使用者帳戶的認證登入。
    
在 [**查看報告**] 頁面上，您可以查看下列類型的報告： 
  
- [稽核報告](#auditing-reports)
- [主管審查報告](#supervisory-review-report)
- [資料外洩防護報告](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>稽核報告

下表說明安全性 & 規範中心的 [**查看報告**] 頁面上的 [**審計**] 區段中的報告。 
  
|**Report**|**描述**|
|:-----|:-----|
|**審核記錄報告** <br/> |您可以在組織中搜尋使用者和系統管理員活動的「審核記錄檔」。 報告包含 Exchange Online 中的使用者和系統管理員活動、SharePoint 線上、商務 OneDrive，以及 Azure Active Directory，也就是 Office 365 的目錄服務。 如需詳細資訊，請參閱[在 Office 365 中搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。  <br/> |
|**Azure AD 報告** <br/> |若要尋找組織中不尋常或可疑的登入活動，您可以在 Microsoft Azure 中使用登入和活動報告。 您也可以在 Azure AD 審核記錄中查看事件。 若要在 Azure 中查看報告，只要按一下 [**查看 AZURE AD 報告**]。 如需詳細資訊，請參閱： <br/><br/>[在 Office 365 中使用您的免費 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)。 <br/> [查看您的存取和使用方式報告](https://go.microsoft.com/fwlink/p/?LinkId=506902)。  <br/> |
|**Exchange 稽核報告** <br/> | 您可以使用 Microsoft 365 中的審計功能追蹤組織管理員對 Exchange Online 設定所做的變更。 Microsoft 資料中心系統管理員或委派的系統管理員也會記錄對 Exchange Online 組織所做的變更。 在 Exchange Online 中，系統管理員審核記錄預設為啟用，因此您不需要執行任何動作即可將其開啟。 Exchange Online 也提供信箱審核記錄，可讓您追蹤信箱擁有者以外的其他人對信箱的存取權。 您必須針對您想要追蹤之非擁有者存取的每個信箱啟用信箱稽核記錄。  <br/>  對於系統管理員及信箱稽核記錄，您可以執行稽核報告，即可檢視稽核記錄項目。 您也可以匯出信箱和系統管理員稽核記錄，這些記錄會在 24 小時內，以 XML 檔案附加在電子郵件訊息中傳送給您。 <br/><br/>如需匯出稽核記錄的詳細資訊，請參閱：  <br/><br/> [匯出信箱稽核記錄](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [查看和匯出資料中心管理員審核記錄](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [搜尋角色群組變更或管理員稽核記錄檔](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange 審核報告](https://go.microsoft.com/fwlink/p/?LinkID=395232)。  <br/> |
   
## <a name="supervisory-review-report"></a>主管審查報告

透過「主管審查」報告，您可以看到組織中所有主管審查原則的狀態。 如需詳細資訊，請參閱[設定組織的主管審查原則](configure-supervision-policies.md)。
  
## <a name="data-loss-prevention-reports"></a>資料外洩防護報告

資料遺失防護（DLP）報告包含已套用至內容之 DLP 原則和規則的相關資訊，這些資訊包含組織中的敏感性資料。 您也可以設定報告，即可顯示根據 DLP 原則和規則之動作的相關資訊。 如需詳細資訊，請參閱[查看資料遺失防護報告](view-the-dlp-reports.md)。
