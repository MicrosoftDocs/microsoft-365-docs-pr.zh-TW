---
title: Microsoft 365 用戶端應用程式支援：條件式存取
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: 在本文中，瞭解哪些平臺、用戶端和 PowerShell 模組支援 Microsoft 365 的條件式存取。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc187a26cd3aa644888312327b07fc9a116950cc
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806679"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Microsoft 365 用戶端應用程式支援：條件式存取

在新式的工作場所，使用者可以使用各種裝置和應用程式從任何地方存取您組織的資源。 因此，只關注可以存取資源的人員，已不再足夠。 您的組織也必須支援在存取控制基礎結構中存取資源的方式和位置。

您可以使用 Azure Active Directory 裝置、位置及多重要素驗證型條件式存取，滿足此新需求。 條件式存取功能是 Azure Active Directory 的功能，可讓您強制存取您環境中應用程式的控制，所有這些都是以特定條件為基礎，並從中心位置進行管理。

深入瞭解 [Azure Active Directory 條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/)。

## <a name="supported-clients--platforms"></a>支援的用戶端 & 平臺

下列用戶端和平臺的最新版本支援條件式存取。 如需 Microsoft 365 平臺支援的詳細資訊，請參閱 [microsoft 365 的系統需求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)。

<br>
<br>

| 用戶端 | Android | iOS | Mac| Windows 10 <br> 新式應用程式| Windows 10 <br> 桌上型電腦 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 系統管理員 | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Access | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Azure 系統管理員 | 不適用 | 不適用 | 不適用 | 不適用 | 不適用 |
| 公司入口網站 | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A |
| Cortana | 計畫 | 計畫 | 不適用 | ![支援](../media/check-mark.png) | N/A |
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
| Power Apps | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | 計畫 | 不適用 |
| 自動功耗 | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Power BI | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| PowerPoint | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Project | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Publisher | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| 商務用 Skype | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 ||
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

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
