---
title: Microsoft 365 用戶端應用程式支援：憑證型驗證
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
description: 在本文中，尋找有關以憑證為基礎之驗證的 Microsoft 365 用戶端應用程式支援的詳細資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 49ed1e329e83b73441c89de9a142bfb9dcac5395
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806691"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 用戶端應用程式支援：憑證型驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

憑證型驗證可讓您使用 Windows、Android 或 iOS 裝置上的用戶端憑證，對 Azure Active Directory 進行驗證。 設定此功能後，您就不需要在行動裝置上的某些郵件和 Microsoft Office 應用程式中輸入使用者名稱和密碼組合。

深入瞭解 [憑證型驗證](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。

## <a name="supported-clients--platforms"></a>支援的用戶端 & 平臺

下列用戶端和平臺的最新版本支援憑證型驗證。 如需 Microsoft 365 平臺支援的詳細資訊，請參閱 [microsoft 365 的系統需求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)。
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
| OneDrive | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 計畫 | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
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
| 線上系統管理員 SharePoint | 計畫 | 計畫 | 不適用 | 不適用 | 不適用 |
| 粘滯音符 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) | N/A |
| Stream | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | 不適用 |
| Sway | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) | N/A |
| Teams | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A | 計畫 |
| To Do | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | N/A |
| Visio | 不適用 | ![支援](../media/check-mark.png) | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Whiteboard | 計畫 | 計畫 | 不適用 | ![支援](../media/check-mark.png) | N/A |
| Word | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| 工作場所分析 | 不適用 | 不適用 | 不適用 | 不適用 | 不適用 |
| Yammer | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 計畫 | 不適用 | 計畫 |

## <a name="supported-powershell-modules"></a>支援的 PowerShell 模組

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

