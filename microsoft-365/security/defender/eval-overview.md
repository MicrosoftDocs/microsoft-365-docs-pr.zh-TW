---
title: 評估和試驗 Microsoft 365 Defender，XDR，以防止、偵測、調查、回應、端點、身分識別、應用程式、電子郵件、共同作業應用程式的資料。
description: 規劃您的 Microsoft 365 Defender 試用實驗室或試驗環境，以測試及體驗設計用來保護裝置、身分識別、資料及應用程式的安全性解決方案。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 06/25/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ade3087543f45439664868fbe02f1746e1f5e762
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457904"
---
# <a name="evaluate-and-pilot-microsoft-365-defender"></a>評估和試驗 Microsoft 365 Defender

**適用於：**

- Microsoft 365 Defender

Microsoft 365 Defender 是一種延伸偵測和回應 (XDR) 解決方案，可自動收集、關聯及分析整個 Microsoft 365 環境（包括端點、電子郵件、應用程式和身分識別）中的信號、威脅及警示資料。 它會利用大量的 AI 和自動化，自動停止攻擊，並將受影響的資產修正為安全狀態。 下列文章會逐步引導您完成設定試用環境的程式，讓您評估 Microsoft 365 Defender 的功能和功能。 

逐步執行這些文章時，步驟將說明如何啟用每個元件、設定設定，以及開始使用試驗群組進行監視。 當您準備好時，您可以將評估環境直接提升為生產環境來完成。 

Microsoft 建議您在 Office 365 的現有實際執行訂閱中建立評估。 這樣一來，您就可以立即獲得實際的洞察力，並調整設定，以應對環境中的目前威脅。 當您獲得經驗並熟悉平臺之後，只要將每個元件一次升級至實際執行。 


## <a name="the-anatomy-of-an-attack"></a>攻擊剖析

Microsoft 365 Defender 是雲端式、整合型、後向和破壞後的企業防護套件。 其跨端點、身分識別、應用程式、電子郵件、共同作業應用程式及其所有資料協調 *防護*、 *偵測*、 *調查* 和 *回應* 。

在此圖中，會進行攻擊。 網路釣魚電子郵件會到達組織中某員工的收件匣，他無意中開啟電子郵件附件。 這會安裝惡意程式碼，這會導致因竊取敏感性資料而造成的事件鏈。 但在此情況下，Office 365 的 Defender 已在運作中。

![Microsoft 365 Defender 如何停止威脅鏈](../../media/defender/m365-defender-eval-threat-chain.png)

在此圖例中：

- **Exchange Online Protection** 的部分 Microsoft Defender Office 365 中，可以偵測網路釣魚電子郵件，並使用郵件流程規則，讓它永遠不會抵達收件匣。
- **Office 365** 安全附件的 Defender 會測試附件，並判斷其是否有害，這樣就不會有到達的郵件，也就是讓郵件無法取得。
- **Defender For Endpoint** 會管理連線到公司網路的裝置，並偵測可能被利用之裝置和網路弱點。
- **用於身分識別的 Defender** 會記下因許可權提升或高風險橫向移動的突然帳戶變更。 此外，它也會報告易於利用的身分識別問題，例如不受限制的 Kerberos 委派，以供安全小組進行修正。
- **Microsoft Cloud App Security** 會發現反常行為，例如不可能的旅行、認證存取，以及不尋常的下載、檔案共用或郵件轉送活動，並向安全性小組報告這些行為。

### <a name="microsoft-365-defender-components"></a>Microsoft 365 Defender 元件

Microsoft 365 Defender 是由這些安全性技術所組成，以串聯運作。 您不需要所有這些元件，就 XDR 和 Microsoft 365 Defender 的功能受益。 您也可以透過使用一或兩種方式來獲得效益和效能。 

|元件  |描述  |參考資料  |
|---------|---------|---------|
|適用於身分識別的 Microsoft Defender     |      Microsoft Defender for Identity 使用 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、已遭破壞的身分識別，以及惡意的有問必答行為。     |     [什麼是適用於身分識別的 Microsoft Defender？](/defender-for-identity/what-is)   |
|Exchange Online Protection     |      Exchange Online Protection 是本機雲端型 SMTP 轉送和篩選服務，可協助您的組織抵禦垃圾郵件和惡意程式碼。      |   [Exchange Online Protection (EOP) 一覽-Office 365](../office-365-security/overview.md)     |
|適用於 Office 365 的 Microsoft Defender     |     Microsoft Defender Office 365 會保護您的組織免受電子郵件訊息、連結 (URLs) 及共同作業工具帶來的惡意威脅。      |    [用於 Office 365 Office 365 的 Microsoft Defender](../office-365-security/overview.md)    |
|適用於端點的 Microsoft Defender     |     Microsoft Defender for Endpoint 是一個整合的平臺，可提供裝置保護、破壞後偵測、自動調查和建議的回應。      |   [Microsoft Defender for Endpoint Windows 安全性](../defender-endpoint/microsoft-defender-endpoint.md)    |
|Microsoft Cloud App Security     |      Microsoft Cloud App security 是完整的跨 SaaS 解決方案，對您的雲端應用程式提供深層的可見度、強資料控制及增強威脅防護。       |    [什麼是 Cloud App Security？](/cloud-app-security/what-is-cloud-app-security)    |
|Azure AD Identity Protection|Azure AD 身分識別保護評估來自數十億美元登入企圖的風險資料，並使用此資料評估每個登入您環境的風險。 Azure AD 使用此資料來允許或防止帳戶存取，視設定條件式存取原則的方式而定。 Azure AD 身分識別保護是與 Microsoft 365 Defender 分開授權。 它附帶 Azure Active Directory Premium P2。|[何謂身分識別保護？](/azure/active-directory/identity-protection/overview-identity-protection)|
| | | |

## <a name="microsoft-365-defender-architecture"></a>Microsoft 365 Defender 架構

下圖說明主要 Microsoft 365 Defender 元件和整合的高層級架構。 每個 Defender 元件和使用案例案例的 *詳細* 架構都是在這系列文章中提供。

![Microsoft 365 Defender 高層級架構](../../media/defender/m365-defender-eval-architecture.png)

在此圖中：

- Microsoft 365 Defender 會組合所有的 Defender 元件中的信號，以提供跨網域的延伸偵測和回應 (XDR) 。 這包括統一的事件佇列、對停止攻擊的自動回應、對受損裝置的自我修復 (、使用者身分識別及信箱) 、跨威脅搜尋和威脅分析。
- Microsoft Defender 會保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具所造成的惡意威脅。 它會與 Microsoft 365 Defender 共用這些活動所產生的信號。 Exchange Online Protection (的 EOP) 已整合，以提供對內送電子郵件和附件的端對端保護。
- Microsoft Defender for Identity 會從執行 Active Directory 同盟服務之伺服器 (AD FS) 和內部部署 Active Directory 網域服務 (AD DS) 收集信號。 它會使用這些信號來保護您的混合式身分識別環境，包括防範使用已遭破壞之帳戶的駭客，以在內部部署環境中的工作站之間移動橫向。
- Microsoft Defender for Endpoint 會從您的組織所用的信號收集和保護裝置。
- Microsoft Cloud App Security 會從您組織的雲端應用程式使用中收集信號，並保護環境和這些應用程式之間的資料流程動，包括 sanctioned 和 unsanctioned 雲端應用程式。
- Azure AD 身分識別保護評估來自數十億美元登入企圖的風險資料，並使用此資料評估每個登入您環境的風險。 Azure AD 使用此資料來允許或防止帳戶存取，視設定條件式存取原則的方式而定。 Azure AD 身分識別保護是與 Microsoft 365 Defender 分開授權。 它附帶 Azure Active Directory Premium P2。  

此圖例中未包含的其他選用架構元件：

- 所有 Microsoft Defender 元件的詳細信號資料都可以整合到 Azure Sentinel 中，並與其他記錄來源合併，以提供完整的 SIEM 和 SOAR 功能及洞察力。

## <a name="the-evaluation-process"></a>評估程式

Microsoft 建議依照所述順序啟用 Microsoft 365 的元件：

![Microsoft 365 Defender 高層級評估程式](../../media/defender/m365-defender-eval-process.png)

下表說明此圖例。

|      |步驟  |描述  |
|------|---------|---------|
|1     | [建立評估環境](eval-create-eval-environment.md)       |此步驟可確保您已具備 Microsoft 365 Defender 的試用版授權。         |
|2      | [啟用適用于身分識別的 Defender](eval-defender-identity-overview.md)        | 查看架構需求、啟用評估，並逐步流覽教程，以找出並修正不同的攻擊類型。   |
|3      | [啟用 Office 365 的 Defender](eval-defender-office-365-overview.md)       | 請確定符合架構需求、啟用評估，然後建立試驗環境。 此元件包含 Exchange Online Protection，因此您會 *在這裡實際* 評價。      |
|4      | [啟用端點的 Defender ](eval-defender-endpoint-overview.md)       | 請確定符合架構需求、啟用評估，然後建立試驗環境。         |
|5      | [啟用 Microsoft Cloud App Security](eval-defender-mcas-overview.md)        |  請確定符合架構需求、啟用評估，然後建立試驗環境。        |
|6      | [調查和回應威脅](eval-defender-investigate-respond.md)        |   模擬攻擊，並開始使用事件回應功能。      |
|7      | [將試用版提升為生產環境](eval-defender-promote-to-production.md)        | 將 Microsoft 365 元件逐一提升為逐個生產。        |
| | | |

這是一種常見的建議順序，其設計目的是以快速的方式取得功能的價值，具體取決於部署及設定功能的一般需要工作量。 例如，Office 365 的 defender，設定的速度可比註冊用於終結點的 defender 裝置所需的速度更快。 當然，您可以設定元件的優先順序以滿足您的業務需求，並以不同順序啟用這些元件。

## <a name="next-steps"></a>後續步驟

[建立 Microsoft 365 Defender 評估環境](eval-create-eval-environment.md)
