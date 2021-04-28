---
title: 跨 Microsoft 365 部署威脅防護功能
description: 深入瞭解 Microsoft 365 E5 中的威脅防護服務和安全性功能。 使用 Microsoft 365 E5 保護您的使用者帳戶、裝置、電子郵件內容等等。
keywords: 方案，設定，高級威脅防護，atp，安全性，microsoft 365 E5，保護裝置，defender，m365
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
ms.openlocfilehash: 04e9ed3d108fa68bdfbf3b34de618d904e3f2cba
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065094"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a><span data-ttu-id="4e5d1-105">跨 Microsoft 365 E5 部署威脅防護功能</span><span class="sxs-lookup"><span data-stu-id="4e5d1-105">Deploy threat protection capabilities across Microsoft 365 E5</span></span>

<span data-ttu-id="4e5d1-106">此解決方案說明跨 Microsoft 365 E5 的強大威脅防護功能，並說明威脅防護很重要的原因。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-106">This solution describes powerful threat protection capabilities across Microsoft 365 E5 and explains why threat protection is important.</span></span> <span data-ttu-id="4e5d1-107">請閱讀本文，以取得 Microsoft 365 E5 威脅防護的概況，以及如何為您的組織進行安裝和設定。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-107">Read this article to get an overview of threat protection in Microsoft 365 E5 and how to approach setup and configuration for your organization.</span></span>

## <a name="why-threat-protection-is-important"></a><span data-ttu-id="4e5d1-108">威脅防護為何很重要</span><span class="sxs-lookup"><span data-stu-id="4e5d1-108">Why threat protection is important</span></span> 

<span data-ttu-id="4e5d1-109">[惡意](/windows/security/threat-protection/intelligence/understanding-malware)代碼和複雜的 cyberattacks （例如 [fileless 威脅](/windows/security/threat-protection/intelligence/fileless-threats)）都是常見的時機。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-109">[Malware](/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="4e5d1-110">企業必須以有效的 IT 安全性功能來保護自己及其客戶。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-110">Businesses need to protect themselves and their customers with effective IT security capabilities.</span></span> <span data-ttu-id="4e5d1-111">Cyberattacks 可能會造成組織的主要問題，包括從失去信任到財務 woes、業務威脅停機等等。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-111">Cyberattacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="4e5d1-112">防護威脅很重要，但決定組織的時間、精力和資源的位置，可能會有很大的難度。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-112">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> <span data-ttu-id="4e5d1-113">Microsoft 365 E5 可提供協助。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-113">Microsoft 365 E5 can help.</span></span> 

<span data-ttu-id="4e5d1-114">Microsoft 的安全性解決方案已內置於我們的產品和服務中。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-114">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="4e5d1-115">「自動化」和「機器學習」功能可減少安全性小組的負載，以確保處理適當的專案。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-115">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="4e5d1-116">Microsoft 安全性解決方案的強項是以 trillions 在我們每天處理的 [智慧安全性圖形](/graph/security-concept-overview)中的信號來建立。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-116">And the strength of Microsoft security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](/graph/security-concept-overview).</span></span> <span data-ttu-id="4e5d1-117">Microsoft 365 的安全性解決方案包括 [microsoft 365 Defender](../security/defender/microsoft-365-defender.md)，此解決方案會透過您的電子郵件、資料、裝置和身分識別，以繪製您組織的高級威脅圖片。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-117">Microsoft 365 security solutions include [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), a solution that brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>

<span data-ttu-id="4e5d1-118">觀看這段影片以獲取部署程序概觀。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-118">Watch this video for an overview of the deployment process.</span></span>
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]


## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="4e5d1-119">Microsoft 365 E5 中的威脅防護</span><span class="sxs-lookup"><span data-stu-id="4e5d1-119">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="4e5d1-120">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 可讓您使用可自我調整的內建智慧來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-120">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="4e5d1-121">使用 Microsoft 365 E5 中的威脅防護功能，您可以偵測並調查內部部署和雲端環境中的高級威脅、受到損害的身分識別和惡意動作。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-121">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="4e5d1-122">在 Microsoft 365 E5 中，預設會整合威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-122">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="4e5d1-123">每項功能的信號增加了偵測及回應威脅的整體能力。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-123">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="4e5d1-124">整合的一組功能可為組織（特別是多國組織）提供最佳保護，與執行非 Microsoft 產品相較。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-124">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="4e5d1-125">下圖說明本文所述的 Microsoft 365 E5 威脅防護服務和功能。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-125">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 365 Defender 簡介](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="4e5d1-127">Microsoft 365 Defender 會將信號和資料一起帶入整合的 [Microsoft 365 安全性中心](/microsoft-365/security/defender/overview-security-center)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-127">Microsoft 365 Defender brings the signals and data together into a [unified Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e5d1-128">![Microsoft 365 Defender 儀表板的概念性插圖](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)</span><span class="sxs-lookup"><span data-stu-id="4e5d1-128">![Conceptual illustration of Microsoft 365 Defender dashboard](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)</span></span>

<span data-ttu-id="4e5d1-129">下圖描述部署這些個別功能的建議路徑。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-129">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4e5d1-130">![M365 威脅防護信號](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)</span><span class="sxs-lookup"><span data-stu-id="4e5d1-130">![M365 threat protection signals](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)</span></span>

|<span data-ttu-id="4e5d1-131">解決方案/功能</span><span class="sxs-lookup"><span data-stu-id="4e5d1-131">Solution/capabilities</span></span>  |<span data-ttu-id="4e5d1-132">描述</span><span class="sxs-lookup"><span data-stu-id="4e5d1-132">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="4e5d1-133">多重要素驗證和條件式存取</span><span class="sxs-lookup"><span data-stu-id="4e5d1-133">Multi-factor authentication and Conditional Access</span></span>     |<span data-ttu-id="4e5d1-134">防護遭到損害的身分識別和裝置。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-134">Protect against compromised identities and devices.</span></span> <span data-ttu-id="4e5d1-135">請從這種保護開始，因為它是基礎。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-135">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="4e5d1-136">此指南中建議的設定包括 Azure AD 身分識別保護為先決條件。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-136">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="4e5d1-137">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4e5d1-137">Microsoft Defender for Identity</span></span>     |  <span data-ttu-id="4e5d1-138">使用內部部署 Active Directory 網域服務的雲端式安全性解決方案 (AD DS) 信號來識別、偵測和調查組織中的高級威脅、遭到破壞的身分識別，以及惡意的內幕程式列動。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-138">A cloud-based security solution that uses your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="4e5d1-139">著重于 Microsoft Defender for Identity，因為它會保護您的內部部署和雲端基礎結構、沒有相依性或必要條件，而且可以提供立即的安全性效益。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-139">Focus on Microsoft Defender for Identity next because it protects your on-premises and cloud infrastructure, has no dependencies or prerequisites, and can provide immediate security benefits.</span></span> | 
|<span data-ttu-id="4e5d1-140">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4e5d1-140">Microsoft Defender for Office 365</span></span>     | <span data-ttu-id="4e5d1-141">保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具帶來的惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-141">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="4e5d1-142">針對惡意程式碼、網路釣魚、欺騙及其他攻擊類型的保護。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-142">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="4e5d1-143">建議您先設定 Microsoft Defender for Office 365，因為變更控制、從委任系統移轉設定，以及其他考慮可能需要較長時間進行部署。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-143">Configuring Microsoft Defender for Office 365 is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <p><span data-ttu-id="4e5d1-144">**附注**：請務必設定所有 Office 365 訂閱中所包含的威脅防護功能 (Exchange Online protection) 。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-144">**NOTE**: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="4e5d1-145">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4e5d1-145">Microsoft Defender for Endpoint</span></span>    | <span data-ttu-id="4e5d1-146">Endpoint protection 平臺，可協助避免、偵測、調查和回應高級威脅。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-146">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span>  <span data-ttu-id="4e5d1-147">Defender for Endpoint 可能需要一些時間才能部署，但設定可與其他功能同時進行。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-147">Defender for Endpoint can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="4e5d1-148">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4e5d1-148">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="4e5d1-149">雲端存取安全性經紀人，用於探索、調查和控管。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-149">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="4e5d1-150">您可以及早啟用 Microsoft Cloud App Security，以開始收集資料和洞察力。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-150">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="4e5d1-151">在您的 SaaS 應用程式中實施資訊和其他有針對性的保護，需要規劃，而且可能需要更多時間。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-151">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="4e5d1-152">具有多個安全小組的組織可以平行執行這些功能。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-152">Organizations who have multiple security teams can implement these capabilities in parallel.</span></span> 

## <a name="plan-to-deploy-your-threat-protection-solution"></a><span data-ttu-id="4e5d1-153">規劃部署威脅防護解決方案</span><span class="sxs-lookup"><span data-stu-id="4e5d1-153">Plan to deploy your threat protection solution</span></span>

<span data-ttu-id="4e5d1-154">下圖說明部署威脅防護功能的高層級流程。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-154">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![部署威脅防護功能的程式](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

<span data-ttu-id="4e5d1-156">若要確定您的組織有可能獲得最佳保護，請使用包含下列步驟的程式來設定和部署您的安全性解決方案：</span><span class="sxs-lookup"><span data-stu-id="4e5d1-156">To make sure your organization has the best protection possible, set up and deploy your security solution with a process that includes the following steps:</span></span>

1. <span data-ttu-id="4e5d1-157">[設定多重要素驗證和條件式存取原則](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-157">[Set up multi-factor authentication and Conditional Access policies](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies).</span></span>
2. <span data-ttu-id="4e5d1-158">[設定 Microsoft Defender 身分識別](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-158">[Configure Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity).</span></span>
3. <span data-ttu-id="4e5d1-159">[開啟 Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-159">[Turn on Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender).</span></span>
4. <span data-ttu-id="4e5d1-160">[設定 Office 365 的 Defender](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-160">[Configure Defender for Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365).</span></span>
5. <span data-ttu-id="4e5d1-161">[設定 Microsoft Defender For Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-161">[Configure Microsoft Defender for Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).</span></span>
6. <span data-ttu-id="4e5d1-162">[設定 Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-162">[Configure Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).</span></span>
7. <span data-ttu-id="4e5d1-163">[監視狀態並採取動作](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-163">[Monitor status and take actions](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions).</span></span>
8. <span data-ttu-id="4e5d1-164">[訓練使用者](deploy-threat-protection-configure.md#step-8-train-users)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-164">[Train users](deploy-threat-protection-configure.md#step-8-train-users).</span></span>

<span data-ttu-id="4e5d1-165">您可以平行設定威脅防護功能，因此，如果您有多個網路安全小組負責不同的服務，則可以同時設定組織的保護功能。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-165">Your threat protection features can be configured in parallel, so if you have multiple network security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="4e5d1-166">下一步</span><span class="sxs-lookup"><span data-stu-id="4e5d1-166">Next step</span></span>

<span data-ttu-id="4e5d1-167">繼續 [跨 Microsoft 365 設定威脅防護功能](deploy-threat-protection-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-167">Continue to [Configure threat protection capabilities across Microsoft 365](deploy-threat-protection-configure.md).</span></span>


