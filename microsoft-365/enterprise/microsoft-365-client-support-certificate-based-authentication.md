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
description: 在本文中，尋找有關以憑證為基礎之驗證之 Microsoft 365 用戶端應用程式支援的詳細資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fde124fcefdf3b949ec35a3b2ed99b15ee36f85e
ms.sourcegitcommit: 2beefb695cead03cc21d6066f589572d3ae029aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349677"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 用戶端應用程式支援：憑證型驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

新式驗證是驗證和授權方法組合的傘條款。 包括：

- **驗證方法**：多重要素驗證;以用戶端憑證為基礎的驗證。
- **授權方法**： Microsoft 的開啟授權 (OAuth) 的實施方式。

新式驗證是透過使用驗證程式庫（如 Active Directory 驗證程式庫 (ADAL) 或 Microsoft 驗證程式庫 (MSAL) ）來啟用。 新式驗證是指用戶端用來驗證和授權 Microsoft 365 資源的存取。 新式驗證利用 OAuth，並為用戶端提供一種安全機制，以存取 Microsoft 365 服務，而不需要存取使用者認證。 在登入時，使用者會直接透過 Azure Active Directory 進行驗證，並接收 return 中的存取/重新整理權杖組。 存取權杖會授與用戶端存取權給 Microsoft 365 租使用者中的適當資源。 當目前的存取權杖到期時，會使用重新整理權杖來取得新的 access 或重新整理權杖。

新式驗證支援不同的驗證機制，類似憑證型驗證。 Windows、Android 或 iOS 裝置上的用戶端可以使用憑證型驗證 (CBA) ，以在裝置上使用用戶端憑證來驗證 Azure Active Directory。 使用憑證來從 Azure Active Directory 取得存取/重新整理權杖，而不是一般的使用者名稱/密碼。

深入瞭解 [憑證型驗證](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。

## <a name="supported-clients--platforms"></a>支援的用戶端 & 平臺

在用戶端 (中登入 Azure Active Directory 帳戶時，下列用戶端和平臺的最新版本都支援憑證型驗證，例如，將帳戶新增至應用程式) 時。 如需 Microsoft 365 平臺支援的詳細資訊，請參閱 [microsoft 365 的系統需求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)。
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
| Edge<sup>1</sup> | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Excel | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) | ![支援](../media/check-mark.png) |
| Exchange Online 系統管理員 | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
| Forms | 不適用 | 不適用 | 不適用 | 不適用 | 不適用 |
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
| 發行者 | 不適用 | 不適用 | 不適用 | 不適用 | ![支援](../media/check-mark.png) |
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

>[!NOTE]
><sup>1</sup> Edge IOS 和 Android 會在帳戶新增流程中支援以憑證為基礎的驗證。 在針對網站（通常是內部網路網站）進行驗證時，iOS 和 Android 的 Edge 不支援以憑證為基礎的驗證。 <br><br>  在此案例中，使用者會流覽至網站 (通常是內部網路) （網站要求使用者透過憑證進行驗證）。 這根本不涉及新式驗證，也不會利用 Microsoft 驗證程式庫。 這是因為 iOS 所產生的限制如下： iOS 阻止協力廠商應用程式存取儲存憑證的系統金鑰鏈 (只有 Apple 應用程式和 [Safari web 視圖控制器](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 可以存取系統金鑰鏈) 。 <br><br> 隨著 Edge 依賴用於呈現網站的 [WebKit](https://developer.apple.com/documentation/webkit) 架構，edge 無法存取系統金鑰鏈，並以憑證選擇顯示使用者。 不幸的是，由於 Apple 的架構而設計。

## <a name="supported-powershell-modules"></a>支援的 PowerShell 模組

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

