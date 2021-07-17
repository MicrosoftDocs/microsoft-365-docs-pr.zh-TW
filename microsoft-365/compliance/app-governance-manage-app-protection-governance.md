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
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a><span data-ttu-id="8b0e6-103">Microsoft Cloud App Security 的應用程式控管附加元件（預覽版）</span><span class="sxs-lookup"><span data-stu-id="8b0e6-103">App governance add-on to Microsoft Cloud App Security (in preview)</span></span>

><span data-ttu-id="8b0e6-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8b0e6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8b0e6-105">網路攻擊變得越來越複雜，因利用您在內部部署和雲端基礎結構中部署應用程式的方式，而建立權限提升、橫向移動和資料外流的起點。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-105">Cyberattacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructures, establishing a starting point for privilege escalation, lateral movement, and exfiltration of your data.</span></span> <span data-ttu-id="8b0e6-106">若要了解潛在風險和停止這些類型的攻擊，您需要獲得貴組織內部的應用程式合規性狀態的清晰可見度，以快速識別應用程式何時出現異常行為以及在這些行為對您的環境、資料和使用者帶來風險時進行回應。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-106">To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture to quickly identify when an app exhibits anomalous behaviors and to respond when these behaviors present risks to your environment, data, and users.</span></span>

<span data-ttu-id="8b0e6-107">Microsoft Cloud App Security 的應用程式控管附加元件功能是一種安全性與原則管理功能，專為啟用 OAuth 的應用程式所設計，可透過 Microsoft Graph API 存取 Microsoft 365 資料。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-107">The app governance add-on feature to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.</span></span> <span data-ttu-id="8b0e6-108">應用程式控管透過可採取動作的深入解析和自動化原則警示和動作，提供這些應用程式及其使用者存取、使用和共用儲存在 Microsoft 365 中敏感性資料之方式的完整可見度、補救和控管。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-108">App governance delivers full visibility, remediation, and governance into how these apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions.</span></span>

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

<span data-ttu-id="8b0e6-109">應用程式控管提供您完整的：</span><span class="sxs-lookup"><span data-stu-id="8b0e6-109">App governance provides you with comprehensive:</span></span>

- <span data-ttu-id="8b0e6-110">**深入解析**：在單一儀表板上查看關於租用戶中 Microsoft 365 平台的所有協力廠商應用程式的視圖。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-110">**Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard.</span></span> <span data-ttu-id="8b0e6-111">您可以查看所有應用程式的狀態和警示活動，並回應或回覆它們。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-111">You can see all the apps’ status and alert activities and react or respond to them.</span></span>
- <span data-ttu-id="8b0e6-112">**控管**：建立適用於應用程式、使用者模式及行為的主動或被動式原則，並保護您的使用者避免使用不符合規範或惡意的應用程式，並限制危險應用程式存取您的資料。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-112">**Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.</span></span>
- <span data-ttu-id="8b0e6-113">**偵測**：當應用程式活動中出現異常情況以及在使用不合規範、惡意或有風險的應用程式時收到警示和通知。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-113">**Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.</span></span>
- <span data-ttu-id="8b0e6-114">**補救**：除了自動補救功能外，請即時使用補救控制項以回覆異常的應用程式活動偵測。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-114">**Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.</span></span>

<span data-ttu-id="8b0e6-115">應用程式控管是以平台為基礎的解決方案，是 Microsoft 365 應用程式生態系統中不可或缺的一部分。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-115">App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem.</span></span> <span data-ttu-id="8b0e6-116">應用程式控管會監督並控管向 Azure Active Directory（Azure AD）註冊的啟用 OAuth 應用程式，並透過 Microsoft Graph API 存取資料。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-116">App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API.</span></span> <span data-ttu-id="8b0e6-117">應用程式控管理提供您應用程式行為控制項，以協助加強 IT 基礎結構的安全性與合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-117">App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.</span></span>

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a><span data-ttu-id="8b0e6-118">應用程式控管初探</span><span class="sxs-lookup"><span data-stu-id="8b0e6-118">A first glimpse at app governance</span></span>

<span data-ttu-id="8b0e6-119">若要查看應用程式控管儀表板，請前往 [https://aka.ms/appgovernance](https://aka.ms/appgovernance)。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-119">To see the app governance dashboard, go to [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span></span> <span data-ttu-id="8b0e6-120">請注意，您的登入帳戶必須具有其中一個[系統管理員角色](app-governance-get-started.md#administrator-roles)，才能檢視任何應用程式控管資料。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-120">Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a><span data-ttu-id="8b0e6-121">Azure AD 和 Microsoft Cloud App Security 的應用程式控管整合</span><span class="sxs-lookup"><span data-stu-id="8b0e6-121">App governance integration with Azure AD and Microsoft Cloud App Security</span></span>

<span data-ttu-id="8b0e6-122">應用程式控管、Microsoft Azure Active Directory (Azure AD) 和 Microsoft Cloud App Security 會收集並提供不同的資料集：</span><span class="sxs-lookup"><span data-stu-id="8b0e6-122">App governance, Azure AD, and Microsoft Cloud App Security collect and provide different data sets:</span></span>

- <span data-ttu-id="8b0e6-123">應用程式控管提供 API 層級的應用程式活動詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-123">App governance provides detailed information about an app’s activity at the API level.</span></span>
- <span data-ttu-id="8b0e6-124">Azure AD 提供基礎應用程式中繼資料，以及有關應用程式登入的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-124">Azure AD provides foundational app metadata and detailed information on sign-ins to apps.</span></span>
- <span data-ttu-id="8b0e6-125">Microsoft Cloud App Security 提供應用程式風險資訊。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-125">Microsoft Cloud App Security provides app risk information.</span></span>

<span data-ttu-id="8b0e6-126">透過跨應用程式控管、Azure AD 和 Microsoft Cloud App Security 分享資訊，您可以在一個入口網站中顯示彙總資訊，並輕鬆連結到另一個入口網站以獲取更多資訊。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-126">By sharing information across app governance, Azure AD, and Microsoft Cloud App Security, you can display aggregate information in one portal and easily link to another portal for more information.</span></span> <span data-ttu-id="8b0e6-127">範例如下：</span><span class="sxs-lookup"><span data-stu-id="8b0e6-127">Here are some examples:</span></span>

- <span data-ttu-id="8b0e6-128">應用程式控管中的應用程式登入資訊：</span><span class="sxs-lookup"><span data-stu-id="8b0e6-128">App sign-in information in app governance:</span></span>

  <span data-ttu-id="8b0e6-129">從應用程式控管入口網站，您可以看見每個應用程式的彙總登入活動，並連結回 Azure Active Directory 系統管理中心，以了解登入事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-129">From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.</span></span>

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- <span data-ttu-id="8b0e6-130">Microsoft Cloud App Security 入口網站中的 API 使用資訊：</span><span class="sxs-lookup"><span data-stu-id="8b0e6-130">API usage information in the Microsoft Cloud App Security portal:</span></span>

  <span data-ttu-id="8b0e6-131">從 Microsoft Cloud App Security 入口網站，您可以看見 API 使用層級和彙總的資料傳輸以及應用程式控管入口網站的連結，以查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-131">From the Microsoft Cloud App Security portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.</span></span>

<span data-ttu-id="8b0e6-132">以下是整合的摘要。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-132">Here's a summary of the integration.</span></span>

![Azure AD 和 Microsoft Cloud App Security 的應用程式控管整合](..\media\manage-app-protection-governance\mapg-integration.png)

<span data-ttu-id="8b0e6-134">此外，應用程式管理會將其警示以訊號傳送給 Microsoft Cloud App Security 和 Microsoft 365 Defender，而應用程式治理會從 Microsoft Cloud App Security 接收警示，以針對應用程式型安全性事件進行更詳細的分析。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-134">Additionally, app governance sends its alerts as signals to Microsoft Cloud App Security and Microsoft 365 Defender, and app governance receives alerts from Microsoft Cloud App Security, to enable more detailed analysis of app-based security incidents.</span></span>

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

## <a name="using-app-governance"></a><span data-ttu-id="8b0e6-135">使用應用程式控管</span><span class="sxs-lookup"><span data-stu-id="8b0e6-135">Using app governance</span></span>

<span data-ttu-id="8b0e6-136">使用應用程式管理以保護您的租用戶及其資料，避免潛在惡意軟體或行為不良的應用程式屬於這三個核心功能：</span><span class="sxs-lookup"><span data-stu-id="8b0e6-136">Using app governance to protect your tenant and its data from potentially malicious or ill-behaved apps falls into these three core capabilities:</span></span>

| <span data-ttu-id="8b0e6-137">功能</span><span class="sxs-lookup"><span data-stu-id="8b0e6-137">Capability</span></span> | <span data-ttu-id="8b0e6-138">描述</span><span class="sxs-lookup"><span data-stu-id="8b0e6-138">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="8b0e6-139">應用程式可見度與深入解析</span><span class="sxs-lookup"><span data-stu-id="8b0e6-139">App visibility and insights</span></span>](app-governance-visibility-insights-overview.md) | <span data-ttu-id="8b0e6-140">取得租用戶中 Microsoft 365 應用程式流量和活動的 360°檢視。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-140">Get a 360° view on traffic and activity of the Microsoft 365 applications in your tenant.</span></span> |
| [<span data-ttu-id="8b0e6-141">強化控管的應用程式原則</span><span class="sxs-lookup"><span data-stu-id="8b0e6-141">App policies for reinforced governance</span></span>](app-governance-app-policies-overview.md) | <span data-ttu-id="8b0e6-142">建立主動式或被動式應用程式原則，這可允許您強制執行 Microsoft 3635 應用程式的管理。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-142">Create proactive or reactive app policies, which will allow you to enforce governance for your Microsoft 3635 apps.</span></span> |
| [<span data-ttu-id="8b0e6-143">偵測和補救</span><span class="sxs-lookup"><span data-stu-id="8b0e6-143">Detection and remediation</span></span>](app-governance-detect-remediate-overview.md) | <span data-ttu-id="8b0e6-144">根據平台偵測警示或由原則產生的偵測警示，監視您的應用程式是否發生異常應用程式行為，並根據應用程式原則設定進行自動或手動補救。</span><span class="sxs-lookup"><span data-stu-id="8b0e6-144">Based on platform detection alerts or policy-generated detection alerts, monitor your apps for anomalous app behavior and remediate them, either automatically based on app policy settings or manually.</span></span> |
|||
