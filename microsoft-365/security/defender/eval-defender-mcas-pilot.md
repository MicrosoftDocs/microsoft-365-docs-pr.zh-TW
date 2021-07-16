---
title: 試驗 Microsoft Cloud App Security，使用 Microsoft 365 Defender，建立試驗群組，設定條件式存取控制，嘗試功能，設定成為 Microsoft 365 Defender 的一部分
description: 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境，以測試及體驗設計用來保護裝置、身分識別、資料及應用程式的安全性解決方案。
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
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457624"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a>使用 Microsoft 365 Defender 的試驗 Microsoft Cloud App Security


**適用於：**
- Microsoft 365 Defender

本文是設定 Microsoft Cloud App Security 評估環境之程式中的[步驟 3](eval-defender-mcas-overview.md)之3。 如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-mcas-overview.md)。

使用下列步驟來設定和設定 Microsoft Cloud App Security 的試驗。


![試驗 Microsoft Cloud App Security 步驟](../../media/defender/m365-defender-mcas-pilot-steps.png)

- 步驟 1. [建立試驗群組—將試驗部署的範圍設為特定使用者群組](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [步驟2。設定保護-條件式存取應用程式控制](#step-2-configure-protection--conditional-access-app-control)
- [步驟3。嘗試功能-逐步指導您的環境以進行保護](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a>步驟 1. 建立試驗群組—將試驗部署的範圍設為特定使用者群組

Microsoft Cloud App Security 可讓您進行部署的範圍。 範圍可讓您選取要監視之應用程式的特定使用者群組，或從監控中排除。 您可以包含或排除使用者群組。 若要設定試驗部署的範圍，請參閱設定 [範圍的部署](/cloud-app-security/scoped-deployment)。


## <a name="step-2-configure-protection--conditional-access-app-control"></a>步驟 2. 設定保護-條件式存取應用程式控制

您可以設定的最強大防護之一是條件式存取應用程式控制。 這需要與 Azure Active Directory (Azure AD) 進行整合。 它可讓您將條件式存取原則（包括 (類似) 裝置）等相關原則套用至您已 sanctioned 的雲端應用程式。 

使用 Microsoft Cloud App Security 來管理 SaaS 應用程式的第一步是探索這些應用程式，然後將它們新增至您的 Azure AD 租使用者。 如果您需要探索協助，請參閱 [探索和管理您網路中的 SaaS 應用程式](/cloud-app-security/tutorial-shadow-it)。 在您探索應用程式之後， [將它們新增至您的 AZURE AD 租](/azure/active-directory/manage-apps/add-application-portal)使用者。

您可以執行下列動作來開始管理：

- 首先，在 Azure AD 中建立新的條件式存取原則，並將其設定為「使用條件式存取應用程式控制」。 這會將要求重新導向至雲端 App 安全性。 您可以建立一個原則，並將所有 SaaS 應用程式新增至此原則。
- 接下來，在雲端 App 安全性中建立會話原則。 針對每個您想要套用的控制項建立一個原則。

如需詳細資訊，包括支援的應用程式和用戶端，請參閱[使用 Microsoft Cloud App Security 條件式存取應用程式控制保護應用程式](/cloud-app-security/proxy-intro-aad)。 

如需原則，請參閱[建議的 SaaS 應用程式 Microsoft Cloud App Security 原則](../office-365-security/mcas-saas-access-policies.md)。 這些原則建立于一組共同的身分 [識別和裝置存取原則](../office-365-security/microsoft-365-policies-configurations.md) 上，建議作為所有客戶的起點。 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a>步驟 3. 嘗試功能-逐步指導您的環境以進行保護 

Microsoft Cloud App Security 檔包括一系列的教程，可協助您探索風險及保護您的環境。 

嘗試雲端 App 安全性教程：

- [偵測到可疑的使用者活動](/cloud-app-security/tutorial-suspicious-activity)
- [調查有風險的使用者](/cloud-app-security/tutorial-ueba)
- [調查危險的 OAuth 應用程式](/cloud-app-security/investigate-risky-oauth)
- [探索和保護機密資訊](/cloud-app-security/tutorial-dlp)
- [保護組織中的任何應用程式即時](/cloud-app-security/tutorial-proxy)
- [封鎖敏感資訊的下載](/cloud-app-security/use-case-proxy-block-session-aad)
- [使用系統管理員隔離來保護您的檔案](/cloud-app-security/use-case-admin-quarantine)
- [在危險動作上需要進行逐步驗證](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a>後續步驟

[在試驗環境中使用 Microsoft 365 Defender 調查和回應](eval-defender-investigate-respond.md)

回到 [[評估 Microsoft Cloud App Security](eval-defender-mcas-overview.md)的總覽

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述