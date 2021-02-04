---
title: Microsoft 365 用戶端應用程式支援：單一 Sign-On
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
description: 在本文中，瞭解哪些平臺、用戶端和 PowerShell 模組支援 Microsoft 365 的單一登入。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a685f04ed64a89cda026ff9380aac7c6c2b3ea4
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097195"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Microsoft 365 用戶端應用程式支援：單一 Sign-On

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

單一登入 (SSO) 會在使用者登入 Azure Active Directory 中的應用程式時，加入安全性和便利性。 使用單一登入時，使用者可以使用一個帳戶登入一次，以存取內部部署 Active Directory 網域服務 (AD DS) 加入網域的裝置、軟體為服務 (SaaS) 應用程式和 web 應用程式。

深入瞭解 [單一登入](/azure/active-directory/manage-apps/what-is-single-sign-on)。

## <a name="supported-clients--platforms"></a>支援的用戶端 & 平臺

下列用戶端和平臺的最新版本支援單一登入。 如需 Microsoft 365 平臺支援的詳細資訊，請參閱 [microsoft 365 的系統需求](/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

| 用戶端 | Android | iOS | Mac| Windows 10 <br> 新式應用程式| Windows 10 <br> 桌上型電腦 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| 公司入口網站 | 不適用 | ![支援](../media/check-mark.png) | 計畫 | ![支援](../media/check-mark.png) | N/A |
| Cortana | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) | N/A |
| Delve | 計畫 | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| 銳利 | ![支援](../media/check-mark.png) | 計畫 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Excel | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Kaizala | ![支援](../media/check-mark.png) | 計畫 | 不適用 | 不適用 | 不適用 |
| Office Lens| ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Office mobile | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Office 入口網站 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) | N/A |
| OneDrive | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 計畫 | ![支援](../media/check-mark.png) | 計畫 |
| OneNote | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 計畫 |
| Outlook | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 計畫 | ![支援](../media/check-mark.png) |
| Planner | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Power Apps | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | 計畫 | 不適用 |
| 自動功耗 | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Power BI | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | 計畫 |
| PowerPoint | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Project | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Publisher | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| 商務用 Skype | 計畫 | 計畫 | 不適用 | 不適用 | 不適用 |
| SharePoint | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| 粘滯音符 | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Stream | 計畫 | 計畫 | 不適用 | 不適用 | 不適用 |
| Sway | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Teams | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 計畫 | 不適用 | 計畫 |
| To Do | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | N/A |
| Visio | 不適用 | ![支援](../media/check-mark.png) | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Whiteboard | 不適用 | ![支援](../media/check-mark.png) | N/A | ![支援](../media/check-mark.png) | N/A |
| Word | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Yammer | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 計畫 |

## <a name="supported-powershell-modules"></a>支援的 PowerShell 模組

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
