---
title: Microsoft 365用戶端應用程式支援：多重要素驗證
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
ms.openlocfilehash: 8749c05e3f7ce5dacf7d3ed1eaa46a46a20482d5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286450"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365用戶端應用程式支援：多重要素驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

若要為登入提供額外的安全性層級，用戶端可以設定為使用多重要素驗證 (MFA) ，它會同時使用使用者密碼及另一個使用者驗證方法，其依據如下：

- 未輕易重複的內容，例如智慧型電話。
- 使用者有唯一和 biologically 的專案，例如其指紋、字型或其他生物統計學屬性

深入瞭解 [多重要素驗證](/azure/active-directory/authentication/multi-factor-authentication)。

## <a name="supported-clients--platforms"></a>支援的用戶端 & 平臺

下列用戶端和平臺的最新版本支援多重要素驗證。 如需 Microsoft 365 中平臺支援的詳細資訊，請參閱[Microsoft 365 的系統需求](/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a>支援的 PowerShell 模組

- [Azure Active DirectoryPowerShell:](/powershell/azure/active-directory/overview)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
