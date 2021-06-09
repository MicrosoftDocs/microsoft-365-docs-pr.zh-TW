---
title: 將帳戶從 Office 365 安全性與合規性中心重新導向至新的 Microsoft 365 Defender
description: 如何從 Office 365 的 defender 重新導向至 Microsoft 365 defender。
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842515"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>將帳戶從 Office 365 安全性與合規性中心重新導向至 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- Microsoft 365 Defender
- 適用於 Office 365 的 Defender

本文說明如何透過從早期 Office 365 安全性與合規性中心自動重新導向 (protection.office.com) ，以 Microsoft 365 Defender (security.microsoft.com) ，將帳戶路由傳送至 Microsoft 365 Defender。

## <a name="what-to-expect"></a>預期的專案
在啟用並使用自動重新導向後，在 Office 365 安全性和合規性 (protection.office.com) 中存取安全性相關功能的使用者，將會自動路由到 Microsoft 365 的 Defender (https://security.microsoft.com) 。  

深入瞭解已變更的專案： [Microsoft 365 Defender 中的 Office 365 的 Microsoft Defender](microsoft-365-security-center-mdo.md)。

開啟自動重新導向時，當使用者使用 Office 365 安全性與合規性中心的安全性功能時，會將使用者路由傳送至 Microsoft 365 Defender。

包括「威脅管理」區段和「威脅管理」儀表板與報告中的功能。 與安全性無關的 Office 365 安全性與合規性中心中的專案不會重新導向至 Microsoft 365 Defender。

可在 Microsoft 365 規範中心內找到相容性相關專案，以及郵件流程相關專案可以在 Exchange 系統管理中心找到。

所有其他功能（不論服務兩者的相容性相關或功能）不會受到重新導向的影響。 Office 365 的安全性警示會出現在 Microsoft 365 Defender 和 Office 365 安全性與合規性中心，但不含重新導向。  

### <a name="set-up-portal-redirection"></a>設定入口網站重新導向
若要在 security.microsoft.com 上開始 Microsoft 365 Defender 的路由帳戶，請執行下列作業：

1. 請確認您是全域系統管理員或具備 Azure Active directory 中的安全性系統管理員許可權。
2. 登[入](https://security.microsoft.com/)Microsoft 365 Defender。
3. 流覽至 **設定**  >  **電子郵件 &** 共同作業  >  **入口網站** 重新導向。  
4. 將自動重新定向設定切換為 [ **開啟**]。
5. 按一下 [**啟用**]，將自動重新導向套用至 Microsoft 365 Defender。

> [!NOTE]
> 在啟用重新導向後，套用此設定時，作用中會話中的帳戶將不會從其會話中彈出，而且只會在結束目前的會話並重新登入後，路由傳送至 Microsoft 365 Defender。

## <a name="can-i-go-back-to-using-the-former-portal"></a>可以回復使用先前的入口網站嗎？
如果有些專案無法運作，或是您的任何專案無法透過 Microsoft 365 Defender 完成，我們想要使用「入口網站意見反應」選項聽取相關專案。 如果您在重新導向時遇到任何問題，請告訴我們。

若要還原為先前的入口網站：

1. 以全域系統管理員身分登[入](https://security.microsoft.com/)以 Microsoft 365 Defender，或在 Azure Active directory 中使用和帳戶搭配安全性管理員許可權。

2. 流覽至 **設定**  >  **電子郵件 &** 共同作業  >  **入口網站** 重新導向。   

3. 將自動重新導向設定切換為 [ **關閉**]。

4. 按一下 [ **停** 用 & 在系統提示時共用意見反應]。

您可以隨時重新啟用此設定。

一旦停用，帳戶將不再路由傳送至 security.microsoft.com，您就會再次存取先前的入口網站（securitycenter 或 securitycenter.microsoft.com）。

## <a name="related-information"></a>相關資訊
- [Microsoft 365Defender 概述](overview-security-center.md)
- [Microsoft 365 defender 中的 Microsoft defender for Endpoint](microsoft-365-security-center-mde.md)
- [Microsoft 提供整合的 SIEM 和 XDR，以現代化的安全性運作](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 和 SIEM 資訊圖表](https://afrait.com/blog/xdr-versus-siem/) 
- [新的 Defender](https://afrait.com/blog/the-new-defender/) 
- [關於 Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 安全性入口網站和系統管理中心](portals.md)
