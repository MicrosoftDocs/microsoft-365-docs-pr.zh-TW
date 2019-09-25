---
title: 安全規範中心內的報告
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: '使用安全&合规性中心获取 SharePoint 联机和交换联机组织的各种报告以及 Azure 活动目录报告。  '
ms.openlocfilehash: 979eb59ed0adf115b9cdda4cd99f97845e9b4b4c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078179"
---
# <a name="reports-in-the-security--compliance-center"></a>安全規範中心內的報告

您可以使用安全&合规性**中心的"查看报告"** 页快速访问 SharePoint 在线和 Exchange 在线组织的审核报告。 还可以**从"查看报告"** 页访问 Azure 活动目录 （AD） 用户登录报告、用户活动报告和 Azure AD 审核日志。 这是因为付费 Office 365 订阅包括 Microsoft Azure 的免费订阅。 首次尝试访问这些 Azure 报表时，必须完成一次性注册过程。 
  
> [!TIP]
> 要查看有关 Office 365 组织中活动的其他报告，请参阅[Microsoft 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。 
  
 **開始之前**
  
您需要以下权限才能在安全&合规性中心查看报告。
  
- 您必须在 Exchange 管理中心 （EAC） 中分配安全读取器角色，才能在安全&合规性中心查看报告。 默认情况下，此角色分配给 EAC 中的组织管理和安全读取器角色组。
    
- 您必须在安全&合规性中心中分配"仅查看 DLP 合规性管理"角色，才能在安全&合规性中心查看 DLP 报告。 默认情况下，此角色分配给安全&合规性中心的合规性管理员、组织管理、安全管理员和安全读取器角色组。

- 此外，您必须在 EAC 中分配"仅查看收件人"角色才能在 EAC 中查看 DLP 报告。 默认情况下，此角色分配给 EAC 中的合规性管理、组织管理和仅查看组织管理角色组。
  
 **要在安全&合规性中心打开"查看报告"页：**
  
1. 請移至 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。
    
2. 使用 Office 365 组织中用户帐户的凭据登录到 Office 365。
    
在"**查看报表"** 页上，您可以查看以下类型的报表： 
  
- [稽核報告](#auditing-reports)
- [监督审查报告](#supervisory-review-report)
- [資料外洩防護報告](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>稽核報告

下表描述了安全&合规中心"**查看报告"** 页上**的"审核"** 部分中的报表。 
  
|**Report**|**描述**|
|:-----|:-----|
|**Office 365 审核日志报告** <br/> |您可以在 Office 365 组织中搜索 Office 365 审核日志中的用户和管理活动。 此报表包含 Exchange 联机、共享点联机、企业 OneDrive 和 Azure 活动目录（Office 365 的目录服务）中的条目用户和管理员活动。 有关详细信息，请参阅在[Office 365 中搜索审核日志。](search-the-audit-log-in-security-and-compliance.md)  <br/> |
|**Azure AD 報告** <br/> |要查找 Office 365 组织中异常或可疑的登录活动，可以在 Microsoft Azure 中使用登录和活动报告。 您还可以在 Azure AD 审核日志中查看事件。 要查看 Azure 中的**报表，只需单击"查看 Azure AD 报告"。** 如需詳細資訊，請參閱： <br/><br/>[在 Office 365 中使用免费的 Azure 活动目录订阅。](use-your-free-azure-ad-subscription-in-office-365.md) <br/> [查看您的访问和使用报告。](http://go.microsoft.com/fwlink/p/?LinkId=506902)  <br/> |
|**Exchange 稽核報告** <br/> | 您可以使用 Office 365 中的审核功能来跟踪组织管理员对 Exchange Online 配置所做的更改。 Microsoft 数据中心管理员或委派管理员对 Exchange Online 组织所做的更改也会被记录。 对于 Exchange Online，管理员审核日志记录默认处于启用状态，因此您无需执行任何操作来打开它。 Exchange Online 还提供邮箱审核日志记录，以便跟踪邮箱所有者以外的人对邮箱的访问。 您必須針對您想要追蹤之非擁有者存取的每個信箱啟用信箱稽核記錄。  <br/>  對於系統管理員及信箱稽核記錄，您可以執行稽核報告，即可檢視稽核記錄項目。 您也可以匯出信箱和系統管理員稽核記錄，這些記錄會在 24 小時內，以 XML 檔案附加在電子郵件訊息中傳送給您。 <br/><br/>如需匯出稽核記錄的詳細資訊，請參閱：  <br/><br/> [匯出信箱稽核記錄](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [查看和导出数据中心管理员审核日志](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [搜尋角色群組變更或管理員稽核記錄檔](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [交换审核报告](http://go.microsoft.com/fwlink/p/?LinkID=395232)。  <br/> |
   
## <a name="supervisory-review-report"></a>监督审查报告

通过监督审核报告，您可以查看组织中所有监督审核策略的状态。 有关详细信息，请参阅[为您的组织配置监督审核策略。](configure-supervision-policies.md)
  
## <a name="data-loss-prevention-reports"></a>資料外洩防護報告

数据丢失防护 （DLP） 报告包含有关已应用于 Office 365 组织中包含敏感数据的内容的 DLP 策略和规则的信息。 您也可以設定報告，即可顯示根據 DLP 原則和規則之動作的相關資訊。 有关详细信息，请参阅[查看报告以预防数据丢失。](view-the-dlp-reports.md)
