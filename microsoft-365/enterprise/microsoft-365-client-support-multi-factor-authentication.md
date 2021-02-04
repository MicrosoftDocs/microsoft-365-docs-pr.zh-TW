---
title: Microsoft 365 用戶端應用程式支援：多重要素驗證
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 在本文中，瞭解哪些平臺、用戶端和 PowerShell 模組支援 Microsoft 365 的多重要素驗證。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097459"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 用戶端應用程式支援：多重要素驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

若要為登入提供額外的安全性層級，用戶端可以設定為使用多重要素驗證 (MFA) ，它會同時使用使用者密碼和其他使用者驗證方法，其依據如下：

- 未輕易重複的內容，例如智慧型電話。
- 使用者有唯一和 biologically 的專案，例如其指紋、字型或其他生物統計學屬性

深入瞭解 [多重要素驗證](/azure/active-directory/authentication/multi-factor-authentication)。

## <a name="supported-clients--platforms"></a>支援的用戶端 & 平臺

下列用戶端和平臺的最新版本支援多重要素驗證。 如需 Microsoft 365 平臺支援的詳細資訊，請參閱 [microsoft 365 的系統需求](/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

| 用戶端 | Android | iOS | Mac| Windows 10 <br> 新式應用程式| Windows 10 <br> 桌上型電腦 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 系統管理員 | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Access | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Azure 系統管理員 | 不適用 | 不適用 | 不適用 | 不適用 | 不適用 |
| 公司入口網站 | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A |
| Cortana | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | N/A |
| Delve | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| 銳利 | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Excel | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Exchange Online 系統管理員 | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| 表單 | 不適用 | 不適用 | 不適用 | 不適用 | 不適用 |
| Office 365 系統管理 | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |  |
| Kaizala | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Office Lens| ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | N/A |
| Office mobile | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Office 入口網站 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) | N/A |
| OneDrive | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| OneNote | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Outlook | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Planner | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Power Apps | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | N/A |
| 自動功耗 | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Power BI | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| PowerPoint | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Project | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Publisher | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| 商務用 Skype | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) |
| 商務用 Skype 系統管理員 | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| SharePoint | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| 線上系統管理員 SharePoint | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| 粘滯音符 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) | N/A |
| Stream | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Sway | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) | N/A |
| Teams | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) |
| To Do | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A |
| Visio | 不適用 | ![支援](../media/check-mark.png) | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Whiteboard | 計畫 | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | N/A |
| Word | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| 工作場所分析 | 不適用 | 不適用 | 不適用 | 不適用 | 不適用 |
| Yammer | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>支援的 PowerShell 模組

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)