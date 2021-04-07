---
title: 設定跨 Microsoft 365 之威脅防護功能的步驟
description: 使用本文作為實施威脅防護解決方案的指南。 在 Microsoft 365 E5 上部署威脅防護服務和功能。
keywords: security，setup，configuration，Microsoft 365 E5，高級威脅防護
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 847dd2d090fb26c5558d4a3496a79cf4829881fb
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604390"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a><span data-ttu-id="07cc3-105">跨 Microsoft 365 設定威脅防護功能</span><span class="sxs-lookup"><span data-stu-id="07cc3-105">Configure threat protection capabilities across Microsoft 365</span></span>

<span data-ttu-id="07cc3-106">請遵循下列步驟來設定跨 Microsoft 365 的威脅防護。</span><span class="sxs-lookup"><span data-stu-id="07cc3-106">Follow these steps to configure threat protection across Microsoft 365.</span></span>

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a><span data-ttu-id="07cc3-107">步驟1：設定多重要素驗證和條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="07cc3-107">Step 1: Set up multi-factor authentication and Conditional Access policies</span></span>

<span data-ttu-id="07cc3-108">[多重要素驗證](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) 要求使用者使用電話或驗證器應用程式來驗證其身分識別。</span><span class="sxs-lookup"><span data-stu-id="07cc3-108">[Multi-factor authentication](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) requires users to verify their identity with a phone call or an authenticator app.</span></span> <span data-ttu-id="07cc3-109">[條件式存取原則](/azure/active-directory/conditional-access/overview) 定義必須滿足的特定需求，使用者才能存取 Microsoft 365 中的應用程式和資料。</span><span class="sxs-lookup"><span data-stu-id="07cc3-109">[Conditional access policies](/azure/active-directory/conditional-access/overview) define certain requirements that must be met in order for users to access apps and data in Microsoft 365.</span></span> <span data-ttu-id="07cc3-110">MFA 和條件式存取原則共同運作，以保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="07cc3-110">MFA and Conditional Access policies work together to protect your organization.</span></span> <span data-ttu-id="07cc3-111">例如，如果有人嘗試使用未啟用 MFA 的帳戶登入行動裝置，且條件式存取原則要求 MFA 生效，該使用者便無法登入。</span><span class="sxs-lookup"><span data-stu-id="07cc3-111">For example, if someone attempts to sign in from a mobile device using an account that is not enabled for MFA, and a Conditional Access policy requires MFA to be in effect, that user is prevented from signing in.</span></span>  

<span data-ttu-id="07cc3-112">Microsoft 已測試並建議一組特定的條件式存取和相關原則，以保護所有 SaaS 應用程式的存取，尤其是 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="07cc3-112">Microsoft has tested and recommends a specific set of Conditional Access and related policies for protecting access to all of your SaaS applications, especially Microsoft 365.</span></span> <span data-ttu-id="07cc3-113">建議使用原則進行基準、機密和高管制的保護。</span><span class="sxs-lookup"><span data-stu-id="07cc3-113">Policies are recommended for baseline, sensitive, and highly regulated protection.</span></span> <span data-ttu-id="07cc3-114">從執行基準保護的原則開始。</span><span class="sxs-lookup"><span data-stu-id="07cc3-114">Begin by implementing the policies for baseline protection.</span></span> 


<span data-ttu-id="07cc3-115">設定身分[ ![ 識別與裝置存取的常見原則，](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [請參閱較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)</span><span class="sxs-lookup"><span data-stu-id="07cc3-115">[![Common policies for configuring identity and device access](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)
[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)</span></span>

### <a name="to-implement-baseline-protection-for-microsoft-365"></a><span data-ttu-id="07cc3-116">若要執行 Microsoft 365 的基準保護</span><span class="sxs-lookup"><span data-stu-id="07cc3-116">To implement baseline protection for Microsoft 365</span></span>

![部署基準保護的程式](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. <span data-ttu-id="07cc3-118">[設定必要條件，包含 AZURE AD Identity Protection](../security/office-365-security/identity-access-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-118">[Configure prerequisites, including Azure AD Identity Protection](../security/office-365-security/identity-access-prerequisites.md).</span></span>
2. <span data-ttu-id="07cc3-119">[設定一般身分識別和裝置存取原則](../security/office-365-security/identity-access-policies.md) ，以進行基準保護。</span><span class="sxs-lookup"><span data-stu-id="07cc3-119">[Configure common identity and device access policies](../security/office-365-security/identity-access-policies.md) for baseline protection.</span></span>
3. <span data-ttu-id="07cc3-120">設定 [來賓使用者](../security/office-365-security/identity-access-policies-guest-access.md)、 [Microsoft 團隊](../security/office-365-security/teams-access-policies.md)、 [Exchange online](../security/office-365-security/secure-email-recommended-policies.md)和 [SharePoint 線上及 OneDrive](../security/office-365-security/sharepoint-file-access-policies.md)的原則。</span><span class="sxs-lookup"><span data-stu-id="07cc3-120">Configure policies for [guest users](../security/office-365-security/identity-access-policies-guest-access.md), [Microsoft Teams](../security/office-365-security/teams-access-policies.md), [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md), and [SharePoint Online and OneDrive](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

### <a name="more-information-about-protecting-identities"></a><span data-ttu-id="07cc3-121">保護身分識別的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="07cc3-121">More information about protecting identities</span></span>

- [<span data-ttu-id="07cc3-122">身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="07cc3-122">Identity and device access configurations</span></span>](../security/office-365-security/microsoft-365-policies-configurations.md)
- [<span data-ttu-id="07cc3-123">Azure MFA 的安全性指導方針</span><span class="sxs-lookup"><span data-stu-id="07cc3-123">Security guidance for Azure MFA</span></span>](/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a><span data-ttu-id="07cc3-124">步驟2：設定 Microsoft Defender 身分識別</span><span class="sxs-lookup"><span data-stu-id="07cc3-124">Step 2: Configure Microsoft Defender for Identity</span></span>

<span data-ttu-id="07cc3-125">[Microsoft Defender For Identity](/defender-for-identity/what-is) 是雲端式的安全性解決方案，可搭配您的內部部署 Active Directory 網域服務與您的內部部署 Active Directory 網域服務 (AD DS) 信號來識別、偵測和調查組織中的高級威脅、遭到破壞的身分識別，以及惡意的內幕程式列動。</span><span class="sxs-lookup"><span data-stu-id="07cc3-125">[Microsoft Defender for Identity](/defender-for-identity/what-is) is a cloud-based security solution that works with your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span>

<span data-ttu-id="07cc3-126">Microsoft Defender for Identity 可讓安全性作業 (SecOps) 分析員和安全性專業人員，以偵測混合式環境中的高級攻擊：</span><span class="sxs-lookup"><span data-stu-id="07cc3-126">Microsoft Defender for Identity enables security operations (SecOps) analysts and security professionals struggling to detect advanced attacks in hybrid environments to:</span></span>
- <span data-ttu-id="07cc3-127">使用以教學為基礎的分析來監控使用者、實體行為和活動。</span><span class="sxs-lookup"><span data-stu-id="07cc3-127">Monitor users, entity behavior, and activities with learning-based analytics.</span></span>
- <span data-ttu-id="07cc3-128">保護儲存在 Active Directory 中的使用者身分識別和認證。</span><span class="sxs-lookup"><span data-stu-id="07cc3-128">Protect user identities and credentials stored in Active Directory.</span></span>
- <span data-ttu-id="07cc3-129">識別並調查整個狙殺鍊中的可疑使用者活動和進階攻擊。</span><span class="sxs-lookup"><span data-stu-id="07cc3-129">Identify and investigate suspicious user activities and advanced attacks throughout the kill chain.</span></span>
- <span data-ttu-id="07cc3-130">以簡單的時間表提供清楚的事件資訊，以進行快速分級。</span><span class="sxs-lookup"><span data-stu-id="07cc3-130">Provide clear incident information on a simple timeline for fast triage.</span></span>

### <a name="to-set-up-microsoft-defender-for-identity"></a><span data-ttu-id="07cc3-131">設定 Microsoft Defender 身分識別</span><span class="sxs-lookup"><span data-stu-id="07cc3-131">To set up Microsoft Defender for Identity</span></span>

![部署 Microsoft Defender 身分識別的程式](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. <span data-ttu-id="07cc3-133">為身分[識別設定 Microsoft Defender](/azure-advanced-threat-protection/install-atp-step1)以保護主要環境。</span><span class="sxs-lookup"><span data-stu-id="07cc3-133">[Set up Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step1) to protect your primary environments.</span></span>
2. <span data-ttu-id="07cc3-134">保護所有的 [網域控制站](/azure-advanced-threat-protection/atp-sensor-monitoring) 和 [樹](/azure-advanced-threat-protection/atp-multi-forest)系。</span><span class="sxs-lookup"><span data-stu-id="07cc3-134">Protect all your [domain controllers](/azure-advanced-threat-protection/atp-sensor-monitoring) and [forests](/azure-advanced-threat-protection/atp-multi-forest).</span></span>
3. <span data-ttu-id="07cc3-135">將 [Microsoft Defender 的身分識別警示](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) 整合到您的安全性作業中 (SecOps) 工作流程。</span><span class="sxs-lookup"><span data-stu-id="07cc3-135">Integrate [Microsoft Defender for Identity alerts](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) into your security operations (SecOps) workflow.</span></span>

### <a name="more-information-about-microsoft-defender-for-identity"></a><span data-ttu-id="07cc3-136">Microsoft Defender 身分識別的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="07cc3-136">More information about Microsoft Defender for Identity</span></span>

- [<span data-ttu-id="07cc3-137">什麼是適用於身分識別的 Microsoft Defender？</span><span class="sxs-lookup"><span data-stu-id="07cc3-137">What is Microsoft Defender for Identity?</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="07cc3-138">影片： Microsoft Defender 身分識別簡介</span><span class="sxs-lookup"><span data-stu-id="07cc3-138">Video: Introduction to Microsoft Defender for Identity</span></span>](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [<span data-ttu-id="07cc3-139">用於身分識別部署的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="07cc3-139">Microsoft Defender for Identity deployment</span></span>](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a><span data-ttu-id="07cc3-140">步驟3：開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07cc3-140">Step 3: Turn on Microsoft 365 Defender</span></span>

<span data-ttu-id="07cc3-141">[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md) 會將信號和分割功能結合成單一解決方案。</span><span class="sxs-lookup"><span data-stu-id="07cc3-141">[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md) combines signals and orchestrates capabilities into a single solution.</span></span> <span data-ttu-id="07cc3-142">透過整合的 Microsoft 365 Defender 解決方案，安全性專業人員可以結合每一種產品接收及決定威脅的完整範圍和影響，以結合威脅。如何進入環境、受到影響的內容，以及目前對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="07cc3-142">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that each of these products receive and determine the full scope and impact of the threat; how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="07cc3-143">Microsoft 365 Defender 採取自動動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="07cc3-143">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span>

<span data-ttu-id="07cc3-144">Microsoft 365 Defender 在工作負載中統一的提醒、事件、自動化調查和回應，以及高級搜尋 (Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 及 Microsoft Cloud App Security) 成為單一玻璃體驗的單一窗格。</span><span class="sxs-lookup"><span data-stu-id="07cc3-144">Microsoft 365 Defender unifies alerts, incidents, automated investigation and response, and advanced hunting across workloads (Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security) into a single pane of glass experience.</span></span> <span data-ttu-id="07cc3-145">新功能會連續新增至 Microsoft 365 Defender;請考慮改為接收預覽功能。</span><span class="sxs-lookup"><span data-stu-id="07cc3-145">New features are added continually to Microsoft 365 Defender; consider opting in to receive preview features.</span></span>

### <a name="to-set-up-microsoft-365-defender"></a><span data-ttu-id="07cc3-146">設定 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07cc3-146">To set up Microsoft 365 Defender</span></span>

![部署 Microsoft 365 Defender 的程式](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. <span data-ttu-id="07cc3-148">[複查必要條件](../security/defender/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-148">[Review the prerequisites](../security/defender/prerequisites.md).</span></span>
2. <span data-ttu-id="07cc3-149">[開啟 Microsoft 365 Defender](../security/defender/m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-149">[Turn on Microsoft 365 Defender](../security/defender/m365d-enable.md).</span></span>
3. <span data-ttu-id="07cc3-150">[加入宣告預覽功能](../security/defender/preview.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-150">[Opt in for preview features](../security/defender/preview.md).</span></span>

### <a name="more-information-about-microsoft-365-defender"></a><span data-ttu-id="07cc3-151">Microsoft 365 Defender 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="07cc3-151">More information about Microsoft 365 Defender</span></span>

- [<span data-ttu-id="07cc3-152">什麼是 Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="07cc3-152">What is Microsoft 365 Defender?</span></span>](../security/defender/microsoft-365-defender.md)
- [<span data-ttu-id="07cc3-153">Microsoft 365 Defender 的新功能</span><span class="sxs-lookup"><span data-stu-id="07cc3-153">What's new in Microsoft 365 Defender</span></span>](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a><span data-ttu-id="07cc3-154">步驟4：設定適用于 Office 的 Microsoft Defender 365</span><span class="sxs-lookup"><span data-stu-id="07cc3-154">Step 4: Configure Microsoft Defender for Office 365</span></span>

<span data-ttu-id="07cc3-155">[Microsoft Defender For Office 365](../security/office-365-security/defender-for-office-365.md) 針對電子郵件中的惡意威脅 (附件和 URLs) 、Office 檔和共同作業工具進行保護。</span><span class="sxs-lookup"><span data-stu-id="07cc3-155">[Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) safeguards your organization against malicious threats in email messages (attachments and URLs), Office documents, and collaboration tools.</span></span> <span data-ttu-id="07cc3-156">下表列出 microsoft 365 E5 包含的 Microsoft Defender for Office 365 功能和功能：</span><span class="sxs-lookup"><span data-stu-id="07cc3-156">The following table lists Microsoft Defender for Office 365 features and capabilities that are included in Microsoft 365 E5:</span></span>

|<span data-ttu-id="07cc3-157">設定、保護及偵測功能</span><span class="sxs-lookup"><span data-stu-id="07cc3-157">Configuration, protection, and detection capabilities</span></span>|<span data-ttu-id="07cc3-158">自動化、調查、修正及教育功能</span><span class="sxs-lookup"><span data-stu-id="07cc3-158">Automation, investigation, remediation, and education capabilities</span></span>|
|:---|:---|
|[<span data-ttu-id="07cc3-159">安全附件</span><span class="sxs-lookup"><span data-stu-id="07cc3-159">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)<br/>[<span data-ttu-id="07cc3-160">安全連結</span><span class="sxs-lookup"><span data-stu-id="07cc3-160">Safe Links</span></span>](../security/office-365-security/safe-links.md)<br/>[<span data-ttu-id="07cc3-161">安全文件</span><span class="sxs-lookup"><span data-stu-id="07cc3-161">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)<br/>[<span data-ttu-id="07cc3-162">適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="07cc3-162">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](../security/office-365-security/mdo-for-spo-odb-and-teams.md)<br/> [<span data-ttu-id="07cc3-163">Microsoft 365 中的反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="07cc3-163">Anti-phishing protection in Microsoft 365</span></span>](../security/office-365-security/anti-phishing-protection.md)|[<span data-ttu-id="07cc3-164">威脅追蹤工具</span><span class="sxs-lookup"><span data-stu-id="07cc3-164">Threat Trackers</span></span>](../security/office-365-security/threat-trackers.md)<br/>[<span data-ttu-id="07cc3-165">威脅總管</span><span class="sxs-lookup"><span data-stu-id="07cc3-165">Threat Explorer</span></span>](../security/office-365-security/threat-explorer.md)<br/>[<span data-ttu-id="07cc3-166">自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="07cc3-166">Automated investigation and response</span></span>](../security/office-365-security/office-365-air.md)<br/>[<span data-ttu-id="07cc3-167">攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="07cc3-167">Attack Simulator</span></span>](../security/office-365-security/attack-simulator.md)|
|

<span data-ttu-id="07cc3-168">透過 Microsoft Defender for Office 365，您組織中的人員可以更安全地溝通和展開電子郵件內容和 Office 檔的威脅防護。</span><span class="sxs-lookup"><span data-stu-id="07cc3-168">With Microsoft Defender for Office 365, people across your organization can communicate and collaborate more securely, with threat protection for their email content and Office documents.</span></span>

### <a name="to-set-up-microsoft-defender-for-office-365"></a><span data-ttu-id="07cc3-169">設定 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="07cc3-169">To set up Microsoft Defender for Office 365</span></span>

![部署 Microsoft Defender for Office 365 的程式](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. <span data-ttu-id="07cc3-171">[安裝和設定您的 Microsoft Defender For Office 365 原則](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-171">[Set up and configure your Microsoft Defender for Office 365 policies](../security/office-365-security/protect-against-threats.md).</span></span>
2. <span data-ttu-id="07cc3-172">[查看和使用您的 Microsoft Defender For Office 365 報告](../security/office-365-security/view-reports-for-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-172">[View and use your Microsoft Defender for Office 365 reports](../security/office-365-security/view-reports-for-mdo.md).</span></span>
3. <span data-ttu-id="07cc3-173">[使用威脅調查和回應功能](../security/office-365-security/office-365-ti.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-173">[Use threat investigation and response capabilities](../security/office-365-security/office-365-ti.md).</span></span>

### <a name="more-information-about-microsoft-defender-for-office-365"></a><span data-ttu-id="07cc3-174">Microsoft Defender for Office 365 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="07cc3-174">More information about Microsoft Defender for Office 365</span></span>

- [<span data-ttu-id="07cc3-175">Microsoft Defender for Office 365 簡介</span><span class="sxs-lookup"><span data-stu-id="07cc3-175">Microsoft Defender for Office 365 overview</span></span>](../security/office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="07cc3-176">Microsoft Defender for Office 365 的新功能</span><span class="sxs-lookup"><span data-stu-id="07cc3-176">What's new in Microsoft Defender for Office 365</span></span>](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="07cc3-177">步驟5：設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="07cc3-177">Step 5: Configure Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="07cc3-178">[Microsoft Defender For Endpoint](/windows/security/threat-protection) 會保護您的組織裝置 (也稱為端點) 從 cyberthreats、高級攻擊和資料違例。</span><span class="sxs-lookup"><span data-stu-id="07cc3-178">[Microsoft Defender for Endpoint](/windows/security/threat-protection) protects your organizations devices (also referred to as endpoints) from cyberthreats, advanced attacks, and data breaches.</span></span> <span data-ttu-id="07cc3-179">安全小組在管理其端點的安全性時，效率會更高。</span><span class="sxs-lookup"><span data-stu-id="07cc3-179">Security teams can be more efficient in managing the security of their endpoints.</span></span> <span data-ttu-id="07cc3-180">穩健的工具可協助組織使用具有 [威脅和弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的漏洞偵測，以不斷處理未經修補的系統。</span><span class="sxs-lookup"><span data-stu-id="07cc3-180">Robust tools help organizations keep up with unpatched systems using  vulnerability detection with [Threat and Vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="07cc3-181">自動偵測和修正功能，例如 [攻擊面降低](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)、 [下一代保護](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)、 [端點偵測和回應](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)，以及 [自動調查和修正](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) ，可協助您保護裝置安全地抵禦惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="07cc3-181">Automated detection and remediation capabilities, such as [attack surface reduction](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction), [next-generation protection](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10), [endpoint detection and response](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response), and [automated investigation and remediation](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) help keep your devices safe from malware.</span></span> <span data-ttu-id="07cc3-182">在這些功能上，客戶可以取得主動通知，並在需要時與 Microsoft 威脅專家（自願加入受管理的搜尋服務的一部分）接洽。</span><span class="sxs-lookup"><span data-stu-id="07cc3-182">On top of these capabilities, customers can get proactive notifications and consult with Microsoft Threat Experts on demand, as part of the opt-in managed hunting service.</span></span> 


### <a name="set-up-microsoft-defender-for-endpoint"></a><span data-ttu-id="07cc3-183">設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="07cc3-183">Set up Microsoft Defender for Endpoint</span></span>

![為端點部署 Microsoft Defender 的程式](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. <span data-ttu-id="07cc3-185">為[Microsoft Defender For Endpoint 準備您的環境](../security/defender-endpoint/deployment-phases.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-185">[Prepare your environment for Microsoft Defender for Endpoint](../security/defender-endpoint/deployment-phases.md).</span></span>

2. <span data-ttu-id="07cc3-186">[部署 Microsoft Defender For Endpoint](../security/defender-endpoint/production-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-186">[Deploy Microsoft Defender for Endpoint](../security/defender-endpoint/production-deployment.md).</span></span>

3. <span data-ttu-id="07cc3-187">[在 Microsoft Defender For Endpoint service 上架](../security/defender-endpoint/onboarding.md)上。</span><span class="sxs-lookup"><span data-stu-id="07cc3-187">[Onboard to the Microsoft Defender for Endpoint service](../security/defender-endpoint/onboarding.md).</span></span>

4. <span data-ttu-id="07cc3-188">[完成最常見的安全性系統管理](../security/defender-endpoint/tvm-security-recommendation.md)工作。</span><span class="sxs-lookup"><span data-stu-id="07cc3-188">[Complete your top security administrative tasks](../security/defender-endpoint/tvm-security-recommendation.md).</span></span>

### <a name="more-information-about-microsoft-defender-for-endpoint"></a><span data-ttu-id="07cc3-189">Microsoft Defender for Endpoint 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="07cc3-189">More information about Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="07cc3-190">[深入瞭解 Microsoft Defender For Endpoint](../security/defender-endpoint/microsoft-defender-endpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-190">[Learn more about Microsoft Defender for Endpoint](../security/defender-endpoint/microsoft-defender-endpoint.md).</span></span>
- <span data-ttu-id="07cc3-191">[嘗試 Microsoft Defender For Endpoint 評估實驗室](../security/defender-endpoint/evaluation-lab.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-191">[Try the Microsoft Defender for Endpoint evaluation lab](../security/defender-endpoint/evaluation-lab.md).</span></span>

## <a name="step-6-configure-microsoft-cloud-app-security"></a><span data-ttu-id="07cc3-192">步驟6：設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="07cc3-192">Step 6: Configure Microsoft Cloud App Security</span></span>

<span data-ttu-id="07cc3-193">[Microsoft Cloud App security](/cloud-app-security) 是雲端存取安全性經紀人，可支援記錄檔收集、API 連接器及反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="07cc3-193">[Microsoft Cloud App Security](/cloud-app-security) is a Cloud Access Security Broker that supports log collection, API connectors, and reverse proxy.</span></span> <span data-ttu-id="07cc3-194">Microsoft Cloud App Security 提供豐富的知名度、控制資料旅行和完善的分析，以在所有雲端服務之間識別及打擊 cyberthreats。</span><span class="sxs-lookup"><span data-stu-id="07cc3-194">Microsoft Cloud App Security provides rich visibility, control over data travel, and sophisticated analytics to identify and combat cyberthreats across all your cloud services.</span></span> <span data-ttu-id="07cc3-195">使用 Microsoft Cloud App Security，您的安全性作業可以保護組織的機密資訊、防範 cyberthreats 和異常、探索及監視存取組織資料的應用程式，以及協助確保組織的雲端應用程式符合規範需求。</span><span class="sxs-lookup"><span data-stu-id="07cc3-195">With Microsoft Cloud App Security, your security operations can protect your organization's sensitive information, protect against cyberthreats and anomalies, discover and monitor apps that access your organization's data, and help make sure your organization's cloud apps meet compliance requirements.</span></span>

### <a name="set-up-microsoft-cloud-app-security"></a><span data-ttu-id="07cc3-196">設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="07cc3-196">Set up Microsoft Cloud App Security</span></span>

![部署 Microsoft Cloud App Security 的程式](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. <span data-ttu-id="07cc3-198">[設定入口網站和其他基本需求](/cloud-app-security/general-setup)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-198">[Set up the portal and other basic requirements](/cloud-app-security/general-setup).</span></span>

2. <span data-ttu-id="07cc3-199">[設定 cloud discovery](/cloud-app-security/set-up-cloud-discovery) 和 [connect 應用程式](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-199">[Set up cloud discovery](/cloud-app-security/set-up-cloud-discovery) and [connect apps](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

3. <span data-ttu-id="07cc3-200">[為特色式應用程式部署條件式存取應用程式控制](/cloud-app-security/proxy-deployment-aad)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-200">[Deploy Conditional Access App Control for featured apps](/cloud-app-security/proxy-deployment-aad).</span></span>

4. <span data-ttu-id="07cc3-201">[使用調查工具及儀表板](/cloud-app-security/investigate)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-201">[Use the investigation tools and dashboards](/cloud-app-security/investigate).</span></span>

### <a name="more-information-about-microsoft-cloud-app-security"></a><span data-ttu-id="07cc3-202">Microsoft Cloud App Security 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="07cc3-202">More information about Microsoft Cloud App Security</span></span>

- <span data-ttu-id="07cc3-203">[查看新的功能與功能](/cloud-app-security/release-notes)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-203">[Review new features and capabilities](/cloud-app-security/release-notes).</span></span>
- <span data-ttu-id="07cc3-204">[深入瞭解 Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-204">[Learn more about Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span></span>

## <a name="step-7-monitor-status-and-take-actions"></a><span data-ttu-id="07cc3-205">步驟7：監控狀態並採取動作</span><span class="sxs-lookup"><span data-stu-id="07cc3-205">Step 7: Monitor status and take actions</span></span>

<span data-ttu-id="07cc3-206">設定並部署威脅防護服務和功能之後，下一步是監視威脅偵測，並採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="07cc3-206">After you have set up and deployed your threat protection services and capabilities, your next step is to monitor threat detections, and take appropriate actions.</span></span> <span data-ttu-id="07cc3-207">您最好的起點是 Microsoft 365 的安全性中心 ([https://security.microsoft.com](https://security.microsoft.com)) ，您可以在其中監視和管理您的所有 Microsoft 身分識別、資料、裝置、應用程式和基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="07cc3-207">Your best starting point is the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)), where you can monitor and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> 

![Microsoft 365 安全性中心](../media/solutions-architecture-center/m365-security-center.png)

<span data-ttu-id="07cc3-209">Microsoft 365 的安全性中心是針對安全性管理員和安全性作業小組而設計。</span><span class="sxs-lookup"><span data-stu-id="07cc3-209">The Microsoft 365 security center is intended for security admins and security operations teams.</span></span> <span data-ttu-id="07cc3-210">在 Microsoft 365 的安全性中心，您可以：</span><span class="sxs-lookup"><span data-stu-id="07cc3-210">In the Microsoft 365 security center, you can:</span></span>
- <span data-ttu-id="07cc3-211">以 [安全得分](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-secure-score)查看組織的整體安全性健康情況。</span><span class="sxs-lookup"><span data-stu-id="07cc3-211">View the overall security health of your organization with [Secure Score](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-secure-score).</span></span>
- <span data-ttu-id="07cc3-212">[監視和查看](../security/defender-endpoint/threat-protection-reports.md) 您的身分識別、資料、裝置、應用程式和基礎結構狀態的報告。</span><span class="sxs-lookup"><span data-stu-id="07cc3-212">[Monitor and view reports](../security/defender-endpoint/threat-protection-reports.md) on the status of your identities, data, devices, apps, and infrastructure.</span></span>
- <span data-ttu-id="07cc3-213">透過 [事件](https://docs.microsoft.com/microsoft-365/security/defender/incident-queue)連接警示上的點。</span><span class="sxs-lookup"><span data-stu-id="07cc3-213">Connect the dots on alerts through [incidents](https://docs.microsoft.com/microsoft-365/security/defender/incident-queue).</span></span>
- <span data-ttu-id="07cc3-214">使用 [自動調查和修正](../security/defender/m365d-autoir.md) 來處理威脅。</span><span class="sxs-lookup"><span data-stu-id="07cc3-214">Use [automated investigation and remediation](../security/defender/m365d-autoir.md) to address threats.</span></span>
- <span data-ttu-id="07cc3-215">[主動搜尋威脅](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview)，例如入侵企圖或破壞您電子郵件、資料、裝置和身分識別的活動。</span><span class="sxs-lookup"><span data-stu-id="07cc3-215">[Proactively hunt for threats](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview), such as intrusion attempts or breach activity affecting your email, data, devices, and identities.</span></span>
- <span data-ttu-id="07cc3-216">透過威脅分析[瞭解最新的攻擊活動](https://docs.microsoft.com/microsoft-365/security/defender/latest-attack-campaigns)和技術。</span><span class="sxs-lookup"><span data-stu-id="07cc3-216">[Understand the latest attack campaigns](https://docs.microsoft.com/microsoft-365/security/defender/latest-attack-campaigns) and techniques with threat analytics.</span></span>
- <span data-ttu-id="07cc3-217">...還有更多！</span><span class="sxs-lookup"><span data-stu-id="07cc3-217">... and more!</span></span>

### <a name="more-information-about-the-microsoft-365-security-center"></a><span data-ttu-id="07cc3-218">Microsoft 365 安全中心的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="07cc3-218">More information about the Microsoft 365 security center</span></span>

- <span data-ttu-id="07cc3-219">[開始使用 Microsoft 365 的安全性中心](../security/defender/overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-219">[Get started with the Microsoft 365 security center](../security/defender/overview-security-center.md).</span></span>
- <span data-ttu-id="07cc3-220">[監視和查看報告](../security/defender/overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-220">[Monitor and view reports](../security/defender/overview-security-center.md).</span></span>
- <span data-ttu-id="07cc3-221">[請參閱 Microsoft 365 中的安全性入口網站](../security/defender/portals.md)。</span><span class="sxs-lookup"><span data-stu-id="07cc3-221">[See the security portals in Microsoft 365](../security/defender/portals.md).</span></span>

## <a name="step-8-train-users"></a><span data-ttu-id="07cc3-222">步驟8：訓練使用者</span><span class="sxs-lookup"><span data-stu-id="07cc3-222">Step 8: Train users</span></span>

<span data-ttu-id="07cc3-223">訓練使用者可將您的使用者與安全性作業小組儲存在許多時間和不滿。</span><span class="sxs-lookup"><span data-stu-id="07cc3-223">Training users can save your users and security operations team much time and frustration.</span></span> <span data-ttu-id="07cc3-224">聰明的使用者不太可能開啟附件或按一下可疑電子郵件訊息中的連結，也很可能避免可疑的網站。</span><span class="sxs-lookup"><span data-stu-id="07cc3-224">Savvy users are less likely to open attachments or click links in questionable email messages, and they are more likely to avoid suspicious websites.</span></span> 

<span data-ttu-id="07cc3-225">Harvard 甘迺迪 School [Cybersecurity 活動手冊](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) 提供好的指導方針，可為組織內的安全性感知建立強大的文化，包括訓練使用者來識別網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="07cc3-225">The Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) provides excellent guidance on establishing a strong culture of security awareness within your organization, including training users to identify phishing attacks.</span></span> 

<span data-ttu-id="07cc3-226">Microsoft 365 提供下列資源，協助您在組織中告知使用者：</span><span class="sxs-lookup"><span data-stu-id="07cc3-226">Microsoft 365 provides the following resources to help inform users in your organization:</span></span>

|<span data-ttu-id="07cc3-227">概念</span><span class="sxs-lookup"><span data-stu-id="07cc3-227">Concept</span></span>  |<span data-ttu-id="07cc3-228">資源</span><span class="sxs-lookup"><span data-stu-id="07cc3-228">Resources</span></span>  |
|---------|---------|
|<span data-ttu-id="07cc3-229">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07cc3-229">Microsoft 365</span></span>     |[<span data-ttu-id="07cc3-230">可自訂的教學路徑</span><span class="sxs-lookup"><span data-stu-id="07cc3-230">Customizable learning pathways</span></span>](/office365/customlearning/) <p><span data-ttu-id="07cc3-231">這些資源可協助您將組織中使用者的訓練放在一起</span><span class="sxs-lookup"><span data-stu-id="07cc3-231">These resources can help you put together training for end users in your organization</span></span>        |
|<span data-ttu-id="07cc3-232">Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="07cc3-232">Microsoft 365 security</span></span> |[<span data-ttu-id="07cc3-233">學習模組：使用 Microsoft 365 內建的智慧安全性保護您的組織</span><span class="sxs-lookup"><span data-stu-id="07cc3-233">Learning module: Secure your organization with built-in, intelligent security from Microsoft 365</span></span>](/learn/modules/security-with-microsoft-365) <p><span data-ttu-id="07cc3-234">此模組可讓您描述 Microsoft 365 安全性功能如何協同運作，並闡明這些安全性功能的優點。</span><span class="sxs-lookup"><span data-stu-id="07cc3-234">This module enables you to describe how Microsoft 365 security features work together and to articulate the benefits of these security features.</span></span> |
|<span data-ttu-id="07cc3-235">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="07cc3-235">Multi-factor authentication</span></span>     | [<span data-ttu-id="07cc3-236">雙步驟驗證：其他驗證頁面為何？</span><span class="sxs-lookup"><span data-stu-id="07cc3-236">Two-step verification: What is the additional verification page?</span></span>](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p><span data-ttu-id="07cc3-237">本文可協助使用者瞭解哪些多重要素驗證，以及如何在您的組織中使用它。</span><span class="sxs-lookup"><span data-stu-id="07cc3-237">This article helps end users understand what multi-factor authentication is and why it's being used at your organization.</span></span>    |

<span data-ttu-id="07cc3-238">除了這項指導之外，Microsoft 也建議您的使用者採取本文所述的動作： [保護您的帳戶和裝置免受駭客和惡意](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)代碼的攻擊。</span><span class="sxs-lookup"><span data-stu-id="07cc3-238">In addition to this guidance, Microsoft recommends that your users take the actions described in this article: [Protect your account and devices from hackers and malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx).</span></span> <span data-ttu-id="07cc3-239">這些動作包括：</span><span class="sxs-lookup"><span data-stu-id="07cc3-239">These actions include:</span></span>
- <span data-ttu-id="07cc3-240">使用強式密碼</span><span class="sxs-lookup"><span data-stu-id="07cc3-240">Using strong passwords</span></span>
- <span data-ttu-id="07cc3-241">保護裝置</span><span class="sxs-lookup"><span data-stu-id="07cc3-241">Protecting devices</span></span> 
- <span data-ttu-id="07cc3-242">在 Windows 10 和 Mac 電腦上啟用非管理裝置的安全性功能 () </span><span class="sxs-lookup"><span data-stu-id="07cc3-242">Enabling security features on Windows 10 and Mac PCs (for unmanaged devices)</span></span>
    
<span data-ttu-id="07cc3-243">Microsoft 也建議您採取下列文章中建議的動作來保護其個人電子郵件帳戶：</span><span class="sxs-lookup"><span data-stu-id="07cc3-243">Microsoft also recommends that users protect their personal email accounts by taking the actions recommended in the following articles:</span></span>
- [<span data-ttu-id="07cc3-244">協助保護您的 Outlook.com 電子郵件帳戶</span><span class="sxs-lookup"><span data-stu-id="07cc3-244">Help protect your Outlook.com email account</span></span>](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [<span data-ttu-id="07cc3-245">使用2步驟驗證保護您的 Gmail 帳戶</span><span class="sxs-lookup"><span data-stu-id="07cc3-245">Protect your Gmail account with 2-step verification</span></span>](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
