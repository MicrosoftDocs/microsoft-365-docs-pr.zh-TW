---
title: Microsoft 365用戶端應用程式支援：憑證型驗證
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
description: 在本文中，將尋找有關憑證型驗證之用戶端應用程式支援 Microsoft 365 的詳細資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bef1a684ba1ebe2eaba90677cd726cc190e342db
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286570"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365用戶端應用程式支援：憑證型驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

新式驗證是驗證和授權方法組合的傘條款。 這些方法包括：

- **驗證方法**：多重要素驗證;以用戶端憑證為基礎的驗證。
- **授權方法**： Microsoft 的開啟授權 (OAuth) 的實施方式。

使用驗證程式庫（如 Active Directory 驗證程式庫 (ADAL) 或 Microsoft 驗證程式庫 (MSAL) ）會啟用新式驗證。 新式驗證是指用戶端用來驗證和授權 Microsoft 365 資源的存取權。 新式驗證使用 OAuth，並提供一種安全機制，讓用戶端可以存取 Microsoft 365 服務，而不需要存取使用者認證。 在登入時，使用者會直接驗證 Azure Active Directory，並接收 return 中的存取/重新整理權杖對。 存取權杖會授與用戶端對 Microsoft 365 承租人中適當資源的存取權。 當目前的存取權杖到期時，會使用重新整理權杖來取得新的 access 或重新整理權杖。

新式驗證支援不同的驗證機制，類似憑證型驗證。 Windows、Android 或 iOS 裝置上的用戶端都可以使用憑證型驗證 (CBA) ，以在裝置上使用用戶端憑證進行驗證，以進行 Azure Active Directory。 憑證是用來從 Azure Active Directory 取得存取/重新整理權杖對，而不是一般的使用者名稱/密碼。

深入瞭解 [憑證型驗證](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。

## <a name="supported-clients--platforms"></a>支援的用戶端 & 平臺

在用戶端 (中登入 Azure Active Directory 帳戶時，下列用戶端和平臺的最新版本都支援憑證型驗證，例如，將帳戶新增至應用程式) 時。 如需 Microsoft 365 中平臺支援的詳細資訊，請參閱[Microsoft 365 的系統需求](/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

> [!NOTE]
> 在帳戶新增流程中，iOS 和 Android 的 Edge 支援以憑證為基礎的驗證。 在針對網站（通常是內部網路網站）進行驗證時，iOS 和 Android 的 Edge 不支援以憑證為基礎的驗證。 <br><br>  在此案例中，使用者會流覽至網站 (通常是內部網路) （網站要求使用者透過憑證進行驗證）。 這根本不涉及新式驗證，也不會利用 Microsoft 驗證程式庫。 這是因為 iOS 所產生的限制如下： iOS 阻止協力廠商應用程式存取儲存憑證的系統金鑰鏈 (只有 Apple 應用程式和 [Safari web 視圖控制器](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 可以存取系統金鑰鏈) 。 <br><br> 隨著 Edge 依賴用於呈現網站的 [WebKit](https://developer.apple.com/documentation/webkit) 架構，edge 無法存取系統金鑰鏈，並以憑證選擇顯示使用者。 不幸的是，由於 Apple 的架構而設計。

## <a name="supported-powershell-modules"></a>支援的 PowerShell 模組

- [Azure Active DirectoryPowerShell:](/powershell/azure/active-directory/overview)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
