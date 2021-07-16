---
title: 複查架構需求和 Microsoft Cloud App Security 的結構，並透過瞭解雲端 App 安全性中的架構來規劃設定及設計 Microsoft 365 Defender
description: Microsoft Cloud App Security 技術圖表說明 Microsoft 365 Defender 中的架構，這會協助您建立試驗環境。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a3fa9670262b90d1566c375680946a131bb9c78a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457608"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-cloud-app-security"></a>回顧 Microsoft Cloud App Security 的架構需求和重要概念


**適用於：**

- Microsoft 365 Defender

本文是為 Microsoft Cloud App Security 和 Microsoft 365 Defender 設定評估環境的程式中的[步驟1，共 3](eval-defender-mcas-overview.md) 。 如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-identity-overview.md)。

在啟用 Microsoft Cloud App Security 之前，請確定您瞭解架構，並且可以符合需求。 

## <a name="understand-the-architecture"></a>了解架構

Microsoft Cloud App Security 是雲端存取安全性經紀人 (CASB) 。 不論您的使用者位於何處，不論其所使用的裝置為何，CASBs 都會以即時從您的企業使用者與雲端資源之間的身分進入代理程式。 Microsoft Cloud App Security 原本會與 Microsoft 安全性功能（包括 Microsoft 365 Defender）整合。 

沒有雲端 App 安全性，您組織使用的雲端應用程式是非受管理及未受保護的，如圖例所示。

![Microsoft Cloud App Security 的架構](../../media/defender/m365-defender-mcas-architecture-a.png)

在此圖例中：
- 組織使用雲端 app 的方式受到監控且不受保護。 
- 這種用法會超出受管理組織內的保護。 

#### <a name="discovering-cloud-apps"></a>探索 cloud app

管理雲端 app 使用的第一個步驟是探索您的組織所使用的雲端應用程式。 下圖說明 cloud discovery 如何與雲端 App 安全性搭配運作。

![Microsoft Cloud App Security-Cloud discovery 的架構](../../media/defender/m365-defender-mcas-architecture-b.png)

在此圖例中，有兩種方法可以用來監視網路流量，以及如何探索您的組織所使用的雲端應用程式。
- 答： 雲端應用程式探索與 Microsoft Defender for Endpoint 本來整合。 Defender for Endpoint 報告從 IT 管理的 Windows 10 裝置存取的雲端應用程式和服務。 
- B。 若要在連接至網路的所有裝置上進行覆蓋率，雲端 App 安全性記錄收集器會安裝在防火牆和其他 proxy 上，以從端點收集資料。 此資料會傳送至雲端 App 安全性以進行分析。

#### <a name="managing-cloud-apps"></a>管理雲端應用程式

在您探索 cloud app 並分析您的組織使用這些應用程式的行為後，即可開始管理所選擇的雲端應用程式。 

![Microsoft Cloud App Security 管理雲端應用程式的架構](../../media/defender/m365-defender-mcas-architecture-c.png)

在此圖中：
- 某些應用程式是 sanctioned 供使用。 這是一種開始管理應用程式的簡易方法。
- 您可以將應用程式連接至應用程式連接器，以啟用更深入的洞察力和控制。 應用程式連接器會使用應用程式提供者的 APIs。


#### <a name="applying-session-controls-to-cloud-apps"></a>將會話控制套用至雲端應用程式

Microsoft Cloud App Security 充當反向 proxy，提供 sanctioned 雲端應用程式的 proxy 存取權。 這可讓雲端 App 安全性套用您所設定的會話控制。 

![Microsoft Cloud App Security Proxy 存取會話控制的架構](../../media/defender/m365-defender-mcas-architecture-d.png)

在此圖中：
- 從組織中的使用者和裝置 sanctioned 雲端應用程式的存取，都是透過雲端 App 安全性進行路由傳送。
- 這種 proxy 存取允許套用會話控制。
- 您未 sanctioned 或明確 unsanctioned 的雲端應用程式不會受到影響。

會話控制可讓您將參數套用到您的組織使用雲端 app 的方式。 例如，如果您的組織使用的是 Salesforce，您可以設定只允許受管理的裝置存取 Salesforce 中組織之資料的會話原則。 較簡單的範例可能是設定原則，以監控來自未受管理裝置的流量，這樣您就可以在套用更嚴格的原則之前分析此流量的風險。

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>使用條件式存取應用程式控制與 Azure AD 整合

您的 Azure AD 租使用者可能已加入 SaaS 應用程式，以強制執行多重要素驗證及其他條件式存取原則。 Microsoft Cloud App Security 原本與 Azure AD 整合。 您只需要設定 Azure AD 中的原則，即可在雲端 App 安全性中使用條件式存取應用程式控制。 這會透過雲端 App 安全性以 proxy 方式路由傳送這些受管理的 SaaS 應用程式的網路流量，這可讓雲端 App 安全性監視此流量，以及套用會話控制。 

![Microsoft Cloud App Security SaaS 應用程式的架構](../../media/defender/m365-defender-mcas-architecture-e.png)

在此圖中：
- SaaS 應用程式會與 Azure AD 租使用者整合。 這可讓 Azure AD 強制執行條件式存取原則，包括多重要素驗證。
- 原則會新增至 Azure Active Directory，以將 SaaS 應用程式的流量導向雲端 App 安全性。 原則會指定要套用此原則 SaaS 應用程式。 因此，azure ad 強制執行套用到這些 SaaS 應用程式的任何條件式存取原則之後，azure ad 便會透過雲端 App 安全性將會話流量導向 (proxy) 。
- 雲端 App 安全性會監控這種流量，並套用系統管理員所設定的任何會話控制原則。 

您可能已使用尚未新增至 Azure AD 的雲端 App 安全性發現並 sanctioned 雲端應用程式。 您可以將這些雲端應用程式新增至您的 Azure AD 租使用者和條件式存取規則的範圍，以充分利用條件式存取應用程式控制。

#### <a name="protecting-your-organization-from-hackers"></a>保護您的組織不受駭客攻擊

雲端 App 安全性自行提供強大的保護。 不過，與 Microsoft 365 Defender 的其他功能一起使用時，雲端 App 安全性會將資料提供給共用信號，以協助停止攻擊。

您有必要將此圖例從概述中重複此 Microsoft 365 Defender 評估與試驗指南。 

![Microsoft 365 Defender 如何停止威脅鏈](../../media/defender/m365-defender-eval-threat-chain.png)

著重于此圖的右側，Microsoft Cloud App Security 會發現反常行為，例如不可能的旅行、認證存取，以及不尋常的下載、檔案共用或郵件轉寄活動，並向安全小組報告這些行為。 因此，雲端 App 安全性協助防止駭客和機密資料 exfiltration 的側向移動。 Microsoft 356 Defender 會將所有元件的信號關聯起來，以提供完整的攻擊案例。

## <a name="understand-key-concepts"></a>瞭解重要概念

下表識別重要概念，在評估、設定及部署 Microsoft Cloud App Security 時，請務必瞭解。


|概念  |描述 |其他資訊  |
|---------|---------|---------|
| 雲端 App 安全性儀錶 板 | 提供組織最重要資訊的概述，並提供更深入調查的連結。        | [使用儀表板 ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| 條件式存取應用程式控制    | 與您的身分識別提供者整合的反向 proxy 架構 (IdP) 提供 Azure AD 條件式存取原則，並選擇性地強制執行會話控制。        |  [使用 Microsoft Cloud App Security 條件式存取應用程式控制來保護應用程式](/cloud-app-security/proxy-intro-aad)       |
|  雲端應用程式目錄   | 雲端應用程式目錄可讓您根據超過80個風險因素的排名及計分的 Microsoft Catalog over 16000 雲端 app 的完整圖片。    |  [使用應用程式風險分數](/cloud-app-security/risk-score)       |
| 雲端探索儀表板    | 雲端探索會分析流量記錄檔，其設計目的是讓您更深入地瞭解如何在組織中使用雲端應用程式，以及提供警示和風險層級。     |  [使用探索的應用程式   ](/cloud-app-security/discovered-apps)    |
|連線的應用程式 |雲端 App 安全性使用「雲端對雲端整合」、「API 連接器」和「即時存取」和「會話」控制，利用我們的條件式應用程式存取控制，為連接的應用程式提供端對端保護。 |[保護連線的應用程式](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>評審架構需求

### <a name="discovering-cloud-apps"></a>探索 cloud app

若要探索您環境中使用的雲端應用程式，您可以執行下列其中一項或兩項操作：

- 與 Microsoft Defender for Endpoint 整合，透過雲端探索快速取得並執行。 這種原生整合可讓您立即開始在網路上的 Windows 10 裝置之間收集雲端流量的資料。
- 若要探索所有連接至網路之裝置存取的所有雲端應用程式，請在防火牆和其他 proxy 上部署雲端 App 安全性的記錄收集器。 這樣會從您的端點收集資料，並將其傳送至雲端 App 安全性以進行分析。 雲端 App 安全性原本會與某些協力廠商 proxy 整合，以取得更多功能。

這些選項包含在 [步驟2。啟用評估環境](eval-defender-mcas-enable-eval.md)。 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>將 Azure AD 條件式存取原則套用至雲端應用程式

條件式存取應用程式控制 (將條件式存取原則套用至雲端 app) 需要與 Azure AD 整合的功能。 這不是雲端 App 安全性開始使用的必要條件。 這是我們建議您在試驗階段（步驟3）嘗試的步驟[。試驗 Microsoft Cloud App Security](eval-defender-mcas-pilot.md)。

## <a name="siem-integration"></a>SIEM 整合

您可以將 Microsoft Cloud App Security 與一般 SIEM server 或 Azure Sentinel 整合，以啟用來自已連線應用程式之警示和活動的集中式監視。 

此外，Azure sentinel 包含的 Microsoft Cloud App Security 連接器，可提供與 Azure Sentinel 的深度整合。 這可讓您不僅能看到您的雲端應用程式，還可取得複雜的分析，以識別及抗擊 cyberthreats，以及控制資料的移動方式。

- [一般 SIEM 整合](/cloud-app-security/siem)
- [從 MCAS 到 Azure Sentinel 的資料流程警示和雲端探索記錄](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>後續步驟

步驟2之3：[為 Microsoft Cloud App Security 啟用評估環境](eval-defender-mcas-enable-eval.md)

回到 [[評估 Microsoft Cloud App Security](eval-defender-mcas-overview.md)的總覽

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述