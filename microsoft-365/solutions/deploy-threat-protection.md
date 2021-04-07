---
title: 跨 Microsoft 365 部署威脅防護功能
description: 深入瞭解 Microsoft 365 E5 中的威脅防護服務和安全性。
keywords: 威脅防護、安全性、E5、cyberattack、惡意程式碼、M365、解決方案
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 922e7b7ea8bceced7085af49485b3479a671d5cd
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599956"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a><span data-ttu-id="f9109-104">跨 Microsoft 365 E5 部署威脅防護功能</span><span class="sxs-lookup"><span data-stu-id="f9109-104">Deploy threat protection capabilities across Microsoft 365 E5</span></span>

<span data-ttu-id="f9109-105">[惡意](/windows/security/threat-protection/intelligence/understanding-malware)代碼和複雜的 cyberattacks （例如 [fileless 威脅](/windows/security/threat-protection/intelligence/fileless-threats)）都是常見的時機。</span><span class="sxs-lookup"><span data-stu-id="f9109-105">[Malware](/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="f9109-106">企業必須以有效的 IT 安全性功能來保護自己及其客戶。</span><span class="sxs-lookup"><span data-stu-id="f9109-106">Businesses need to protect themselves and their customers with effective IT security capabilities.</span></span> <span data-ttu-id="f9109-107">Cyberattacks 可能會造成組織的主要問題，包括從失去信任到財務 woes、業務威脅停機等等。</span><span class="sxs-lookup"><span data-stu-id="f9109-107">Cyberattacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="f9109-108">防護威脅很重要，但決定組織的時間、精力和資源的位置，可能會有很大的難度。</span><span class="sxs-lookup"><span data-stu-id="f9109-108">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> 

<span data-ttu-id="f9109-109">Microsoft 的安全性解決方案已內置於我們的產品和服務中。</span><span class="sxs-lookup"><span data-stu-id="f9109-109">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="f9109-110">「自動化」和「機器學習」功能可減少安全性小組的負載，以確保處理適當的專案。</span><span class="sxs-lookup"><span data-stu-id="f9109-110">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="f9109-111">Microsoft 安全性解決方案的強項是以 trillions 在我們每天處理的 [智慧安全性圖形](/graph/security-concept-overview)中的信號來建立。</span><span class="sxs-lookup"><span data-stu-id="f9109-111">And the strength of Microsoft security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](/graph/security-concept-overview).</span></span> <span data-ttu-id="f9109-112">Microsoft 365 的安全性解決方案包括 [microsoft 365 Defender](../security/defender/microsoft-365-defender.md)，此解決方案會透過您的電子郵件、資料、裝置和身分識別，以繪製您組織的高級威脅圖片。</span><span class="sxs-lookup"><span data-stu-id="f9109-112">Microsoft 365 security solutions include [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), a solution that brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>

<span data-ttu-id="f9109-113">觀看這段影片以獲取部署程序概觀。</span><span class="sxs-lookup"><span data-stu-id="f9109-113">Watch this video for an overview of the deployment process.</span></span>
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]


## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="f9109-114">Microsoft 365 E5 中的威脅防護</span><span class="sxs-lookup"><span data-stu-id="f9109-114">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="f9109-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 可讓您使用可自我調整的內建智慧來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="f9109-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="f9109-116">使用 Microsoft 365 E5 中的威脅防護功能，您可以偵測並調查內部部署和雲端環境中的高級威脅、受到損害的身分識別和惡意動作。</span><span class="sxs-lookup"><span data-stu-id="f9109-116">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="f9109-117">在 Microsoft 365 E5 中，預設會整合威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="f9109-117">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="f9109-118">每項功能的信號增加了偵測及回應威脅的整體能力。</span><span class="sxs-lookup"><span data-stu-id="f9109-118">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="f9109-119">整合的一組功能可為組織（特別是多國組織）提供最佳保護，與執行非 Microsoft 產品相較。</span><span class="sxs-lookup"><span data-stu-id="f9109-119">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="f9109-120">下圖說明本文所述的 Microsoft 365 E5 威脅防護服務和功能。</span><span class="sxs-lookup"><span data-stu-id="f9109-120">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 365 Defender 簡介](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="f9109-122">Microsoft 365 Defender 會將信號和資料一起帶入整合的 [Microsoft 365 安全性中心](/microsoft-365/security/defender/overview-security-center)。</span><span class="sxs-lookup"><span data-stu-id="f9109-122">Microsoft 365 Defender brings the signals and data together into a [unified Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span> 

![Microsoft 365 Defender 儀表板的概念性插圖](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

<span data-ttu-id="f9109-124">下圖描述部署這些個別功能的建議路徑。</span><span class="sxs-lookup"><span data-stu-id="f9109-124">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

![M365 威脅防護信號](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|<span data-ttu-id="f9109-126">解決方案/功能</span><span class="sxs-lookup"><span data-stu-id="f9109-126">Solution/capabilities</span></span>  |<span data-ttu-id="f9109-127">描述</span><span class="sxs-lookup"><span data-stu-id="f9109-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f9109-128">多重要素驗證和條件式存取</span><span class="sxs-lookup"><span data-stu-id="f9109-128">Multi-factor authentication and Conditional Access</span></span>     |<span data-ttu-id="f9109-129">防護遭到損害的身分識別和裝置。</span><span class="sxs-lookup"><span data-stu-id="f9109-129">Protect against compromised identities and devices.</span></span> <span data-ttu-id="f9109-130">請從這種保護開始，因為它是基礎。</span><span class="sxs-lookup"><span data-stu-id="f9109-130">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="f9109-131">此指南中建議的設定包括 Azure AD 身分識別保護為先決條件。</span><span class="sxs-lookup"><span data-stu-id="f9109-131">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="f9109-132">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f9109-132">Microsoft Defender for Identity</span></span>     |  <span data-ttu-id="f9109-133">利用內部部署 Active Directory 網域服務 (AD DS) 信號來識別、偵測和調查您組織中的高級威脅、已遭破壞的身分識別和惡意有問必答行動的雲端式安全性解決方案。</span><span class="sxs-lookup"><span data-stu-id="f9109-133">A cloud-based security solution that leverages your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="f9109-134">著重于 Microsoft Defender for Identity，因為它會保護您的內部部署和雲端基礎結構、沒有相依性或必要條件，而且可以提供立即的安全性效益。</span><span class="sxs-lookup"><span data-stu-id="f9109-134">Focus on Microsoft Defender for Identity next because it protects your on-premises and cloud infrastructure, has no dependencies or prerequisites, and can provide immediate security benefits.</span></span> | 
|<span data-ttu-id="f9109-135">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f9109-135">Microsoft Defender for Office 365</span></span>     | <span data-ttu-id="f9109-136">保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具帶來的惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="f9109-136">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="f9109-137">針對惡意程式碼、網路釣魚、欺騙及其他攻擊類型的保護。</span><span class="sxs-lookup"><span data-stu-id="f9109-137">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="f9109-138">建議您先設定 Microsoft Defender for Office 365，因為變更控制、從委任系統移轉設定，以及其他考慮可能需要較長時間進行部署。</span><span class="sxs-lookup"><span data-stu-id="f9109-138">Configuring Microsoft Defender for Office 365 is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <p><span data-ttu-id="f9109-139">**附注**：請務必設定所有 Office 365 訂閱中所包含的威脅防護功能 (Exchange Online protection) 。</span><span class="sxs-lookup"><span data-stu-id="f9109-139">**NOTE**: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="f9109-140">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f9109-140">Microsoft Defender for Endpoint</span></span>    | <span data-ttu-id="f9109-141">Endpoint protection 平臺，可協助避免、偵測、調查和回應高級威脅。</span><span class="sxs-lookup"><span data-stu-id="f9109-141">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span>  <span data-ttu-id="f9109-142">Defender for Endpoint 可能需要一些時間才能部署，但設定可與其他功能同時進行。</span><span class="sxs-lookup"><span data-stu-id="f9109-142">Defender for Endpoint can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="f9109-143">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f9109-143">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="f9109-144">雲端存取安全性經紀人，用於探索、調查和控管。</span><span class="sxs-lookup"><span data-stu-id="f9109-144">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="f9109-145">您可以及早啟用 Microsoft Cloud App Security，以開始收集資料和洞察力。</span><span class="sxs-lookup"><span data-stu-id="f9109-145">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="f9109-146">在您的 SaaS 應用程式中實施資訊和其他有針對性的保護，需要規劃，而且可能需要更多時間。</span><span class="sxs-lookup"><span data-stu-id="f9109-146">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="f9109-147">具有多個安全小組的組織可以平行執行這些功能。</span><span class="sxs-lookup"><span data-stu-id="f9109-147">Organizations who have multiple security teams can implement these capabilities in parallel.</span></span> 

## <a name="deploy-your-threat-protection-solution"></a><span data-ttu-id="f9109-148">部署威脅防護解決方案</span><span class="sxs-lookup"><span data-stu-id="f9109-148">Deploy your threat protection solution</span></span>

 <span data-ttu-id="f9109-149">下圖說明部署威脅防護功能的高層級流程。</span><span class="sxs-lookup"><span data-stu-id="f9109-149">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![部署威脅防護功能的程式](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

<span data-ttu-id="f9109-151">若要確定您的組織有可能獲得最佳保護，請使用包含下列步驟的程式來設定和部署您的安全性解決方案：</span><span class="sxs-lookup"><span data-stu-id="f9109-151">To make sure your organization has the best protection possible, set up and deploy your security solution with a process that includes the following steps:</span></span>

1. [<span data-ttu-id="f9109-152">設定多重要素驗證和條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f9109-152">Set up multi-factor authentication and Conditional Access policies</span></span>](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [<span data-ttu-id="f9109-153">設定 Microsoft Defender 身分識別</span><span class="sxs-lookup"><span data-stu-id="f9109-153">Configure Microsoft Defender for Identity</span></span>](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [<span data-ttu-id="f9109-154">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9109-154">Turn on Microsoft 365 Defender</span></span>](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [<span data-ttu-id="f9109-155">設定 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="f9109-155">Configure Defender for Office 365</span></span>](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [<span data-ttu-id="f9109-156">設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f9109-156">Configure Microsoft Defender for Endpoint</span></span>](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [<span data-ttu-id="f9109-157">設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f9109-157">Configure Microsoft Cloud App Security</span></span>](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [<span data-ttu-id="f9109-158">監視狀態並採取動作</span><span class="sxs-lookup"><span data-stu-id="f9109-158">Monitor status and take actions</span></span>](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [<span data-ttu-id="f9109-159">訓練使用者</span><span class="sxs-lookup"><span data-stu-id="f9109-159">Train users</span></span>](deploy-threat-protection-configure.md#step-8-train-users)

<span data-ttu-id="f9109-160">您可以平行設定威脅防護功能，因此，如果您有多個網路安全小組負責不同的服務，則可以同時設定組織的保護功能。</span><span class="sxs-lookup"><span data-stu-id="f9109-160">Your threat protection features can be configured in parallel, so if you have multiple network security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="f9109-161">下一步</span><span class="sxs-lookup"><span data-stu-id="f9109-161">Next step</span></span>


![部署威脅防護功能的程式](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

<span data-ttu-id="f9109-163">繼續 [設定跨 Microsoft 365 的威脅防護功能](deploy-threat-protection-configure.md)</span><span class="sxs-lookup"><span data-stu-id="f9109-163">Proceed to [Configure threat protection capabilities across Microsoft 365](deploy-threat-protection-configure.md)</span></span>

