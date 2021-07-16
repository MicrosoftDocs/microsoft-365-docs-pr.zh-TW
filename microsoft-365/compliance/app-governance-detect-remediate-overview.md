---
title: 了解應用程式威脅偵測和補救
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 了解應用程式威脅偵測和補救。
ms.openlocfilehash: 26cd8501fdd8bd828357f8adb7d4e90f96e70114
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420076"
---
# <a name="learn-about-app-threat-detection-and-remediation"></a>了解應用程式威脅偵測和補救

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

透過 Microsoft 應用程式控管，您可以：

- 輕鬆監控內建應用程式控管偵測方法針對惡意應用程式活動產生的威脅警示，以及您建立的作用中應用程式原則產生的原則型警示。 這些警示可能表示應用程式活動中的異常情況以及何時使用不合規、惡意或有風險的應用程式。  您還可以在警示中使用模式來建立新的應用程式原則，或修改現有原則的設定以進行更嚴格的動作。
- 在調查後手動或透過作用中應用程式原則上的動作設定，輕鬆自動補救警示。


>[!Note]
>來自未授予存取 Microsoft 365 資源權限的僅 Azure 應用程式的異常活動不包括在應用控管偵測和警示中。
>

請參閱[系統管理員角色](app-governance-get-started.md#administrator-roles)，以取得可存取應用程式控管頁面的角色。


## <a name="app-governance-integration-with-azure-active-directory-and-microsoft-cloud-app-security"></a>與 Azure Active Directory 和 Microsoft 雲端 App 安全性的應用程式控管整合

應用程式控管、Azure Active Directory (Azure AD) 和 Microsoft 雲端 App 安全性會收集並提供不同的資料集：

- Azure AD 提供基礎應用程式中繼資料，以及有關應用程式登入的詳細資訊。
- 應用程式控管提供 API 層級的應用程式活動詳細資訊。
- Microsoft 雲端 App 安全性提供應用程式風險資訊。

透過跨應用程式控管、Azure AD 和 Microsoft 雲端 App 安全性分享資訊，您可以在一個入口網站中顯示彙總資訊，並輕鬆連結到另一個入口網站以獲取更多資訊。 範例如下：

- 應用程式控管中的應用程式登入資訊：

  從應用程式控管入口網站，您可以看見每個應用程式的彙總登入活動，並連結回 Azure Active Directory 系統管理中心，以了解登入事件的詳細資料。

- Azure Active Directory 系統管理中心的應用程式 API 使用資訊：

  從 Azure Active Directory 系統管理中心，您可以看見彙總的應用程式使用資訊，以及應用程式控管入口網站的連結，以了解應用程式使用狀況的詳細資料。

- Microsoft 雲端 App 安全性入口網站中的 API 使用資訊： 

  從 Microsoft 雲端 App 安全性入口網站，您可以看見 API 使用層級和彙總的資料傳輸以及應用程式控管入口網站的連結，以查看詳細資料。

以下是整合的摘要。

![Azure AD 和 Microsoft 雲端 App 安全性的應用程式控管整合](..\media\manage-app-protection-governance\mapg-integration.png)

此外，應用程式控管會將其警示以訊號傳送給 Microsoft 雲端 App 安全性和 Microsoft 365 Defender，以針對應用程式型安全性事件進行更詳細的分析。

<!--

CFA #3 Scenario 1:  As an admin, I can investigate alerts associated to my M365 apps through MAPG.
CFA #3 Scenario 2: As an admin, I can manually remediate 
CFA #3 Scenario 3: As an admin, I can configure policies to perform automatic 
--> 

## <a name="next-step"></a>下一個步驟

[開始使用應用程式威脅偵測和補救。](app-governance-detect-remediate-get-started.md)
