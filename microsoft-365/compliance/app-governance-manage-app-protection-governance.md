---
title: Microsoft 365 中的共同作業控管
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 實施 Microsoft 應用程式控管功能以控管您的應用程式。
ms.openlocfilehash: 63bd6684bc041c3c82ba6b8ddcc28c2600182b26
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430693"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Microsoft Cloud App Security 的應用程式控管附加元件（預覽版）

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

網路攻擊變得越來越複雜，因利用您在內部部署和雲端基礎結構中部署應用程式的方式，而建立權限提升、橫向移動和資料外流的起點。 若要了解潛在風險和停止這些類型的攻擊，您需要獲得貴組織內部的應用程式合規性狀態的清晰可見度，以快速識別應用程式何時出現異常行為以及在這些行為對您的環境、資料和使用者帶來風險時進行回應。

Microsoft Cloud App Security 的應用程式控管附加元件功能是一種安全性與原則管理功能，專為啟用 OAuth 的應用程式所設計，可透過 Microsoft Graph API 存取 Microsoft 365 資料。 應用程式控管透過可採取動作的深入解析和自動化原則警示和動作，提供這些應用程式及其使用者存取、使用和共用儲存在 Microsoft 365 中敏感性資料之方式的完整可見度、補救和控管。

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

應用程式控管提供您完整的：

- **深入解析**：在單一儀表板上查看關於租用戶中 Microsoft 365 平台的所有協力廠商應用程式的視圖。 您可以查看所有應用程式的狀態和警示活動，並回應或回覆它們。
- **控管**：建立適用於應用程式、使用者模式及行為的主動或被動式原則，並保護您的使用者避免使用不符合規範或惡意的應用程式，並限制危險應用程式存取您的資料。
- **偵測**：當應用程式活動中出現異常情況以及在使用不合規範、惡意或有風險的應用程式時收到警示和通知。
- **補救**：除了自動補救功能外，請即時使用補救控制項以回覆異常的應用程式活動偵測。

應用程式控管是以平台為基礎的解決方案，是 Microsoft 365 應用程式生態系統中不可或缺的一部分。 應用程式控管會監督並控管向 Azure Active Directory（Azure AD）註冊的啟用 OAuth 應用程式，並透過 Microsoft Graph API 存取資料。 應用程式控管理提供您應用程式行為控制項，以協助加強 IT 基礎結構的安全性與合規性狀態。

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a>應用程式控管初探

若要查看應用程式控管儀表板，請前往 [https://aka.ms/appgovernance](https://aka.ms/appgovernance)。 請注意，您的登入帳戶必須具有其中一個[系統管理員角色](app-governance-get-started.md#administrator-roles)，才能檢視任何應用程式控管資料。

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>Azure AD 和 Microsoft Cloud App Security 的應用程式控管整合

應用程式控管、Microsoft Azure Active Directory (Azure AD) 和 Microsoft Cloud App Security 會收集並提供不同的資料集：

- 應用程式控管提供 API 層級的應用程式活動詳細資訊。
- Azure AD 提供基礎應用程式中繼資料，以及有關應用程式登入的詳細資訊。
- Microsoft Cloud App Security 提供應用程式風險資訊。

透過跨應用程式控管、Azure AD 和 Microsoft Cloud App Security 分享資訊，您可以在一個入口網站中顯示彙總資訊，並輕鬆連結到另一個入口網站以獲取更多資訊。 範例如下：

- 應用程式控管中的應用程式登入資訊：

  從應用程式控管入口網站，您可以看見每個應用程式的彙總登入活動，並連結回 Azure Active Directory 系統管理中心，以了解登入事件的詳細資料。

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Microsoft Cloud App Security 入口網站中的 API 使用資訊：

  從 Microsoft Cloud App Security 入口網站，您可以看見 API 使用層級和彙總的資料傳輸以及應用程式控管入口網站的連結，以查看詳細資料。

以下是整合的摘要。

![Azure AD 和 Microsoft Cloud App Security 的應用程式控管整合](..\media\manage-app-protection-governance\mapg-integration.png)

此外，應用程式管理會將其警示以訊號傳送給 Microsoft Cloud App Security 和 Microsoft 365 Defender，而應用程式治理會從 Microsoft Cloud App Security 接收警示，以針對應用程式型安全性事件進行更詳細的分析。

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a>使用應用程式控管

使用應用程式管理以保護您的租用戶及其資料，避免潛在惡意軟體或行為不良的應用程式屬於這三個核心功能：

| 功能 | 描述 |
|:-------|:-----|
| [應用程式可見度與深入解析](app-governance-visibility-insights-overview.md) | 取得租用戶中 Microsoft 365 應用程式流量和活動的 360°檢視。 |
| [強化控管的應用程式原則](app-governance-app-policies-overview.md) | 建立主動式或被動式應用程式原則，這可允許您強制執行 Microsoft 3635 應用程式的管理。 |
| [偵測和補救](app-governance-detect-remediate-overview.md) | 根據平台偵測警示或由原則產生的偵測警示，監視您的應用程式是否發生異常應用程式行為，並根據應用程式原則設定進行自動或手動補救。 |
|||
