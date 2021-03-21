---
title: 從商務用 Skype 與 Exchange 移除或停用混合式新式驗證
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文說明如何從商務用 Skype 和 Exchange 中移除或停用混合式新式驗證。
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927285"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>從商務用 Skype 與 Exchange 移除或停用混合式新式驗證

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

如果您已啟用混合式新式驗證 (HMA) 找到它不適用於您目前的環境，您可以停用 HMA。 本文說明如何進行。
  
## <a name="who-is-this-article-for"></a>本文的人選是誰？

如果您已在商務用 Skype Online 或內部部署和/或 Exchange Online 或內部部署中啟用新式驗證，且找到您需要停用 HMA，這些步驟適用于您。

> [!IMPORTANT]
> 若您是在商務用 Skype Online 或內部部署中，請參閱「[新式驗證支援的商務用 skype 拓撲](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)」文章，其具有混合拓撲 HMA，您必須先查看支援的拓撲，再開始。
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>如何停用混合式新式驗證 (Exchange) 

1. **Exchange 內部部署**：開啟 Exchange 管理命令介面，並執行下列命令： 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange online**：以遠端 PowerShell [連接至 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) 。 執行下列命令，將您的  *OAuth2ClientProfileEnabled*  旗標轉換為 "false"：

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>如何停用 (商務用 Skype) 的混合式新式驗證

1. **商務用 skype 內部部署**：在商務用 Skype 管理命令介面中執行下列命令：

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **商務用 Skype online**：使用遠端 PowerShell [連接至商務用 skype online](manage-skype-for-business-online-with-microsoft-365-powershell.md) 。 執行下列命令以停用新式驗證：

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[連結回新式驗證概述](hybrid-modern-auth-overview.md) 。 
