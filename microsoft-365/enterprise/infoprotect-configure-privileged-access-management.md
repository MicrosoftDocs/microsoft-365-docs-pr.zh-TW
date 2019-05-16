---
title: 步驟 6： 設定 Office 365 的特殊權限的存取管理
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 了解及設定 Office 365 的特殊權限存取管理。
ms.openlocfilehash: fdfb0bc69d1dc05cffd717951cb493995d2123d4
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072093"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a>步驟 6： 設定 Office 365 的特殊權限的存取管理

*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 和進階合規性版本*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

特殊權限存取管理的啟用方法是透過設定原則，該原則會指定您的 Office 365 租用戶中工作型活動的 Just-In-Time 存取。它可以協助保護貴組織免於受到使用現有特殊權限系統管理員帳戶與機密資料的常設存取權或關鍵組態設定之存取權的缺口。例如，您可能會設定特殊權限存取管理原則，該原則需要明確核准的存取權，並且會變更您的 Office 365 租用戶中的組織信箱設定。

在這個步驟中，您會在 Office 365 租用戶中啟用特殊權限存取管理，並且設定特殊權限存取原則，該原則為 Office 365 資料的工作型存取以及貴組織的組態設定，提供額外的安全性。在您的 Office 365 組織中開始使用特殊權限存取有三個基本步驟：
- 建立核准者的群組
- 啟用特殊權限存取
- 建立核准原則

一旦設定，特殊權限存取管理就會讓貴組織以零常設特殊權限來運作，並且針對由於此類常設系統管理存取而引發的漏洞提供一層防護。特殊權限存取需要對執行具有已定義相關聯核准原則的工作進行核准。需要執行包含在核准原則內工作的使用者必須要求存取核准並且獲得授與，才能夠具有執行原則中定義工作的必要權限。

若要啟用 Office 365 特殊權限存取管理，請參閱[在 Office 365 中設定特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (機器翻譯) 主題。

如需詳細資訊，請參閱 [Office 365 中的特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) (機器翻譯) 主題。

## <a name="results"></a>結果

這個步驟的結果是您藉由針對貴組織的關鍵資料和組態設定啟用 Just-In-Time 存取控制，增強了 Office 365 的安全性。

作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step6)。

## <a name="next-step"></a>下一步

[資訊保護基礎結構的允出準則](infoprotect-exit-criteria.md)