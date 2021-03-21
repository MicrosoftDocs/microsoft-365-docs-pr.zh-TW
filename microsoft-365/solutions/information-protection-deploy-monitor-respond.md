---
title: 監視和回應組織中的資料隱私權事件
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用審核和警示原則及資料主體要求來監視及回應個人資料事件。
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928421"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>監視和回應組織中的資料隱私權事件

Microsoft 365 的功能可協助您在 operationalize 相關功能時，監控、調查組織中的資料隱私權事件，並加以回應。 針對上述各項，具有程式、程式和其他檔，對規章主體的符合性也很重要。

包括： 

- 審核和警示原則
- 資料主體要求 (包括內容搜尋和 eDiscovery) 
- 其他調查工具和報告

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>資料隱私權規定會影響監控和回應工具的使用

以下是可能與資訊管理控制相關之資料隱私權法規的範例清單：

- LGPD 文章46
- LGPD 文章48
- GDPR 文章 (5)  (1)  (f) 
- GDPR 文章 (15)  (1)  (e) 
- HIPAA-高科技 (45 C.F.R。 164.308 ()  (1)  (ii)  (D) ) 
- HIPAA-高科技 (45 C.F.R。 164.308 ()  (6)  (ii) 
- HIPAA-高科技 (45 C.F.R。 164.312 (b) ) 
- CCPA (1798.105 (c) ) 

如需詳細資訊，請參閱 [評估資料隱私權風險及識別敏感資訊](information-protection-deploy-assess.md)。

資料隱私權規定一般會呼叫下列以進行監視和回應：

- 與儲存、共用及處理個人資料相關的活動的審計、警示和報告
- 在 (DSR) 中回應資料主體要求的能力，在某些情況下，請執行調查和其他管理措施，以遵守這類要求。

您的組織可能也想要針對其他目的（如其他法規遵從性需求或商務原因）執行監視和回應活動。 在整體監控和回應規劃、實施及管理等情況下，建立您的監控和回應架構，以進行資料隱私權。

為了協助您開始使用 Microsoft 365 的監控和回應架構以取得資料隱私權規定，本文會列出 Microsoft 365 中有用的功能，以回答下列問題： 

- 在不同的資料類型和來源中，可以使用哪一天的監視、調查和報表技巧？
- 處理資料主體要求 (Dsr) 及任何補救措施（如匿名、密文和刪除）時，所需的機制。

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>安全性與合規性中心內的審計和警示原則

請參閱下列文章以設定審核、高級審核及警示原則：

- [整合的稽核](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [信箱稽核](../compliance/enable-mailbox-auditing.md)
- [高級審計](../compliance/advanced-audit.md)
- [警示原則](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的資料主體要求

請參閱 [GDPR 和 CCPA 的資料主體要求](/compliance/regulatory/gdpr-dsr-Office365) ，以取得在 Microsoft 365 中回應 DSR 的資訊。

## <a name="manage-deleted-users-in-microsoft-stream"></a>在 Microsoft Stream 中管理已刪除的使用者

在 Microsoft Stream 中，當使用者從 Azure Active Directory (Azure AD) 中刪除時，如果其名稱在該點之前與發佈的資料流程影片相關聯，則其電子郵件地址仍會與影片產生關聯。 請參閱 [管理從 Microsoft Stream 刪除的使用者](/stream/managing-deleted-users) 以將其移除。

## <a name="insider-risk-management-as-an-investigative-tool"></a>以調查工具為內部的內幕風險管理

[365 microsoft 的內幕風險管理](../compliance/insider-risk-management.md) 是 microsoft 規範系統管理中心的一項功能，可讓您偵測、調查和採取行動，以應對組織中的危險活動，以儘量降低內部風險。