---
title: 將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 Defender
description: 如何將帳戶和會話從 Defender to Endpoint 重新導向至 Microsoft 365 defender。
keywords: Microsoft 365Microsoft 365 defender、安全性中心重新導向的 defender （快速入門）
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842563"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender
- 適用於端點的 Defender

在與 microsoft 的跨網域方法進行威脅防護時，SIEM 及擴充偵測和回應 (XDR) ，我們已 rebranded Microsoft Defender 進階威脅防護為 Microsoft Defender for Endpoint，並將其整合到單一整合入口網站-Microsoft 365 Defender。

本指南說明如何透過從先前的 Microsoft Defender for 端點入口網站自動重新導向 (securitycenter.windows.com 或 securitycenter.microsoft.com) 的方式，將帳戶路由至 Microsoft 365 defender，以 Microsoft 365 Defender 入口網站 (security.microsoft.com) 。

> [!NOTE]
> Microsoft 365 defender 中的 Microsoft defender for Endpoint 支援在[microsoft defender security center 中授](./mssp-access.md)與存取[受管理的安全性服務提供者 (MSSPs) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)的方式。

## <a name="what-to-expect"></a>預期的專案
啟用自動重新導向後，在 securitycenter.windows.com 或 securitycenter.microsoft.com 存取先前的 Microsoft Defender for Endpoint 入口網站的帳戶將會自動路由到 security.microsoft.com 的 Microsoft 365 Defender 入口網站。
 
深入瞭解已變更的專案： [Microsoft 365 defender 中的端點的 Microsoft defender](microsoft-365-security-center-mde.md)。

這包括透過瀏覽器直接存取先前入口網站的重新導向，包含指向前 securitycenter.windows.com 入口網站的連結，例如電子郵件通知中的連結，以及 SIEM API 通話傳回的連結。  

 電子郵件通知或 SIEM APIs 中的外部連結目前包含這兩個入口網站的連結。 一旦啟用重新導向，這兩個連結將指向 Microsoft 365 Defender，直到舊的連結最終移除為止。 我們鼓勵您採用指向 Microsoft 365 Defender 的新連結。

如需有關連結和路由的詳細資訊，請參閱下表。
## <a name="siem-api-routing"></a>SIEM API 路由

|**屬性**  |**關閉重新定向時的目的地**  |**重新導向時的目的地** | 
|---------|---------|---------|
| LinkToWDATP | Securitycenter.windows.com 中的警示頁面 | Security.microsoft.com 中的警示頁面  |
| IncidentLinkToWDATP | Securitycenter.windows.com 中的 [事件] 頁面  | Security.microsoft.com 中的 [事件] 頁面  |
| LinkToMTP | Security.microsoft.com 中的警示頁面 | Security.microsoft.com 中的警示頁面  |
| IncidentLinkToMTP | Security.microsoft.com 中的 [事件] 頁面  | Security.microsoft.com 中的 [事件] 頁面  

## <a name="email-alert-notifications"></a>電子郵件警示通知

|**屬性**  |**關閉重新定向時的目的地**  |**重新導向時的目的地** |
|---------|---------|---------|
| 警示頁面  | Securitycenter.windows.com 中的警示頁面  | Security.microsoft.com 中的警示頁面  |
| 事件頁面  |Securitycenter.windows.com 中的 [事件] 頁面  | Security.microsoft.com 中的 [事件] 頁面  
| 安全性中心入口網站中的警示頁面 | Security.microsoft.com 中的警示頁面 | Security.microsoft.com 中的警示頁面 | 
| 安全中心入口網站中的 [事件] 頁面 | Security.microsoft.com 中的 [事件] 頁面  | Security.microsoft.com 中的 [事件] 頁面  |

## <a name="when-does-this-take-effect"></a>何時會生效？ 
一旦啟用，此更新幾乎會立即對某些帳戶生效。 但重新導向可能需要較長的時間，才會傳播至組織中的每個帳戶。 在套用此設定時，作用中會話中的帳戶將不會從其會話中彈出，而且只會在結束其目前的會話之後傳送至 Microsoft 365 Defender，然後重新登入。  

### <a name="set-up-portal-redirection"></a>設定入口網站重新導向
若要開始 Microsoft 365 Defender 的路由帳戶：
1. 確定您是全域系統管理員或具備 Azure Active directory 中的安全性系統管理員許可權 

2. 登[入](https://security.microsoft.com/)Microsoft 365 Defender。

3. 流覽至 **設定**  >  **端點**  >  **一般**  >  **入口** 重新導向或 [按一下這裡](https://security.microsoft.com/preferences2/portal_redirection)。  

4. 將自動重新定向設定切換為 [ **開啟**]。

5. 按一下 [**啟用**]，將自動重新導向套用至 Microsoft 365 Defender。

>[!IMPORTANT]
>啟用此設定不會終止作用中的使用者會話。 在套用此設定的情況下，在使用此設定的使用中的帳戶，只會在結束目前的會話並登入後，導向 Microsoft 365 Defender。

>[!NOTE]
>您必須是全域系統管理員或具備 Azure Active Directory 中的安全性系統管理員許可權，才可啟用或停用此設定。  

## <a name="can-i-go-back-to-using-the-former-portal"></a>可以回復使用先前的入口網站嗎？
如果有些專案無法運作，或是您有任何無法透過 Microsoft 365 Defender 完成的專案，我們想要聽說。 如果您在重新導向時遇到任何問題，我們會建議您使用提供意見反應提交表單，讓我們知道。

若要還原為先前的 Microsoft Defender 端點入口網站：

1. 以全域系統管理員身分登[入](https://security.microsoft.com/)以 Microsoft 365 Defender，或在 Azure Active directory 中使用和帳戶搭配安全性管理員許可權。

2. 流覽至 **設定**  >  **端點**  >  **一般**  >  **入口** 重新導向或 [開啟此頁面](https://security.microsoft.com/preferences2/portal_redirection)。  

3. 將自動重新導向設定切換為 [ **關閉**]。

4. 按一下 [ **停** 用 & 在系統提示時共用意見反應]。

您可以隨時重新啟用此設定。 

一旦停用，帳戶將不再路由傳送至 security.microsoft.com，而您將會再次存取先前的入口網站-securitycenter.windows.com 或 securitycenter.microsoft.com。 

## <a name="related-information"></a>相關資訊
- [Microsoft 365Defender 概述](overview-security-center.md)
- [Microsoft 365 defender 中的 Microsoft defender for Endpoint](microsoft-365-security-center-mde.md)
- [Microsoft 提供整合的 SIEM 和 XDR，以現代化的安全性運作](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 和 SIEM 資訊圖表](https://afrait.com/blog/xdr-versus-siem/) 
- [新的 Defender](https://afrait.com/blog/the-new-defender/) 
- [關於 Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 安全性入口網站和系統管理中心](portals.md)