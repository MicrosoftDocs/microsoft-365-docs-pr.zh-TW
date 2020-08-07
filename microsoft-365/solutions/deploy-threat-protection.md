---
title: 跨 Microsoft 365 部署威脅防護功能
description: 瞭解如何在 Microsoft 365 E5 中部署威脅防護服務和功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 312df25bf4fe2b91bb60b4122378b4457b25723c
ms.sourcegitcommit: b812771805c8b9e92b64deb1928e265e60d80405
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588181"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a><span data-ttu-id="fede7-103">跨 Microsoft 365 部署威脅防護功能</span><span class="sxs-lookup"><span data-stu-id="fede7-103">Deploy threat protection capabilities across Microsoft 365</span></span>

<span data-ttu-id="fede7-104">[惡意](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)代碼和複雜的 cyberattacks （例如[fileless 威脅](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)）都是常見的時機。</span><span class="sxs-lookup"><span data-stu-id="fede7-104">[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="fede7-105">企業必須保護自己及其客戶。</span><span class="sxs-lookup"><span data-stu-id="fede7-105">Businesses need to protect themselves and their customers.</span></span> <span data-ttu-id="fede7-106">網路安全性攻擊可能會造成組織的主要問題，包括從失去信任到財務 woes、業務威脅停機等等。</span><span class="sxs-lookup"><span data-stu-id="fede7-106">Cyber security attacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="fede7-107">防護威脅很重要，但決定組織的時間、精力和資源的位置，可能會有很大的難度。</span><span class="sxs-lookup"><span data-stu-id="fede7-107">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> 

<span data-ttu-id="fede7-108">Microsoft 的安全性解決方案已內置於我們的產品和服務中。</span><span class="sxs-lookup"><span data-stu-id="fede7-108">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="fede7-109">「自動化」和「機器學習」功能可減少安全性小組的負載，以確保處理適當的專案。</span><span class="sxs-lookup"><span data-stu-id="fede7-109">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="fede7-110">Microsoft 安全性解決方案的強項是以 trillions 在我們每天處理的[智慧安全性圖形](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)中的信號來建立。</span><span class="sxs-lookup"><span data-stu-id="fede7-110">And the strength of Microsoft security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph).</span></span> <span data-ttu-id="fede7-111">Microsoft 365 的安全性解決方案包括[Microsoft 威脅防護](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)，這會在您的電子郵件、資料、裝置和身分識別間的信號，以繪製對您組織的高級威脅的圖片。</span><span class="sxs-lookup"><span data-stu-id="fede7-111">Microsoft 365 security solutions include [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), which brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>

<span data-ttu-id="fede7-112">觀賞這段影片，瞭解部署程式的概況。</span><span class="sxs-lookup"><span data-stu-id="fede7-112">Watch this video for an overview of the deployment process.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

<span data-ttu-id="fede7-113">使用本文作為實施威脅防護解決方案的指南。</span><span class="sxs-lookup"><span data-stu-id="fede7-113">Use this article as a guide for implementing your threat protection solution.</span></span>

## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="fede7-114">Microsoft 365 E5 中的威脅防護</span><span class="sxs-lookup"><span data-stu-id="fede7-114">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="fede7-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab)可讓您使用可自我調整的內建智慧來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="fede7-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="fede7-116">使用 Microsoft 365 E5 中的威脅防護功能，您可以偵測並調查內部部署和雲端環境中的高級威脅、受到損害的身分識別和惡意動作。</span><span class="sxs-lookup"><span data-stu-id="fede7-116">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="fede7-117">在 Microsoft 365 E5 中，預設會整合威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="fede7-117">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="fede7-118">每項功能的信號增加了偵測及回應威脅的整體能力。</span><span class="sxs-lookup"><span data-stu-id="fede7-118">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="fede7-119">整合的一組功能可為組織（特別是多國組織）提供最佳保護，與執行非 Microsoft 產品相較。</span><span class="sxs-lookup"><span data-stu-id="fede7-119">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="fede7-120">下圖說明本文所述的 Microsoft 365 E5 威脅防護服務和功能。</span><span class="sxs-lookup"><span data-stu-id="fede7-120">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 威脅防護的概述](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="fede7-122">一旦您部署任何高級威脅防護功能，您就可以開啟 Microsoft 威脅防護，使信號和資料集中在一個位置。</span><span class="sxs-lookup"><span data-stu-id="fede7-122">As soon as you deploy any of the advanced threat protection capabilities, you can turn on Microsoft Threat Protection, which brings the signals and data together into one place.</span></span> 

![Microsoft 威脅防護儀表板的概念性插圖](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

<span data-ttu-id="fede7-124">下圖描述部署這些個別功能的建議路徑。</span><span class="sxs-lookup"><span data-stu-id="fede7-124">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

![M365 威脅防護信號](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|<span data-ttu-id="fede7-126">解決方案/功能</span><span class="sxs-lookup"><span data-stu-id="fede7-126">Solution/capabilities</span></span>  |<span data-ttu-id="fede7-127">描述</span><span class="sxs-lookup"><span data-stu-id="fede7-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fede7-128">多重要素驗證和條件式存取</span><span class="sxs-lookup"><span data-stu-id="fede7-128">Multi-factor authentication and conditional access</span></span>     |<span data-ttu-id="fede7-129">防護遭到損害的身分識別和裝置。</span><span class="sxs-lookup"><span data-stu-id="fede7-129">Protect against compromised identities and devices.</span></span> <span data-ttu-id="fede7-130">請從這種保護開始，因為它是基礎。</span><span class="sxs-lookup"><span data-stu-id="fede7-130">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="fede7-131">此指南中建議的設定包括 Azure AD 身分識別保護為先決條件。</span><span class="sxs-lookup"><span data-stu-id="fede7-131">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="fede7-132">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="fede7-132">Azure Advanced Threat Protection</span></span>     |  <span data-ttu-id="fede7-133">以雲端為基礎的安全性解決方案，可利用您的內部部署 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、遭到破壞的身分識別，以及惡意的內幕程式列動。</span><span class="sxs-lookup"><span data-stu-id="fede7-133">A cloud-based security solution that leverages your on-premises Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="fede7-134">著重于 Azure 高級威脅防護接下來，因為它會保護您的部署和雲端基礎結構、沒有相依性或必要條件，而且可提供立即的利益。</span><span class="sxs-lookup"><span data-stu-id="fede7-134">Focus on Azure Advanced Threat Protection next because it protects your on-prem and your cloud infrastructure, has no dependencies or prerequisites, and can provide immediate benefit.</span></span>       | 
|<span data-ttu-id="fede7-135">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="fede7-135">Office 365 Advanced Threat Protection</span></span>     | <span data-ttu-id="fede7-136">保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具帶來的惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="fede7-136">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="fede7-137">針對惡意程式碼、網路釣魚、欺騙及其他攻擊類型的保護。</span><span class="sxs-lookup"><span data-stu-id="fede7-137">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="fede7-138">建議您先設定 Office 365 的高級威脅防護，因為變更控制會從委任系統移轉設定，而其他考慮可能需要較長時間進行部署。</span><span class="sxs-lookup"><span data-stu-id="fede7-138">Configuring Office 365 Advanced Threat Protection is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <br><br><span data-ttu-id="fede7-139">附注：請務必設定所有 Office 365 訂閱中所包含的威脅防護功能 (Exchange Online Protection) 。</span><span class="sxs-lookup"><span data-stu-id="fede7-139">Note: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="fede7-140">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="fede7-140">Microsoft Defender Advanced Threat Protection</span></span>    | <span data-ttu-id="fede7-141">Endpoint protection 平臺，可協助避免、偵測、調查和回應高級威脅。</span><span class="sxs-lookup"><span data-stu-id="fede7-141">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="fede7-142">Microsoft Defender 高級威脅防護可能需要一些時間才能部署，但設定可與其他功能同時進行。</span><span class="sxs-lookup"><span data-stu-id="fede7-142">Microsoft Defender Advanced Threat Protection can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="fede7-143">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fede7-143">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="fede7-144">雲端存取安全性經紀人，用於探索、調查和控管。</span><span class="sxs-lookup"><span data-stu-id="fede7-144">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="fede7-145">您可以及早啟用 Microsoft Cloud App Security，以開始收集資料和洞察力。</span><span class="sxs-lookup"><span data-stu-id="fede7-145">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="fede7-146">在您的 SaaS 應用程式中實施資訊和其他有針對性的保護，需要規劃，而且可能需要更多時間。</span><span class="sxs-lookup"><span data-stu-id="fede7-146">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="fede7-147">具有多個安全小組的組織可以並存執行這些功能。</span><span class="sxs-lookup"><span data-stu-id="fede7-147">Organizations with multiple security teams can implement these capabilities in parallel.</span></span>

## <a name="deploy-your-threat-protection-solution"></a><span data-ttu-id="fede7-148">部署威脅防護解決方案</span><span class="sxs-lookup"><span data-stu-id="fede7-148">Deploy your threat protection solution</span></span>

<span data-ttu-id="fede7-149">若要確定您的組織有可能獲得最佳保護，請安裝並部署您的安全性解決方案，以包含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fede7-149">To make sure your organization has the best protection possible, set up and deploy your security solution to include the following steps:</span></span>

1. [<span data-ttu-id="fede7-150">設定多重要素驗證和條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="fede7-150">Set up multi-factor authentication and conditional access policies</span></span>](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [<span data-ttu-id="fede7-151">設定 Azure 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="fede7-151">Configure Azure Advanced Threat Protection</span></span>](deploy-threat-protection-configure.md#step-2-configure-azure-advanced-threat-protection)
3. [<span data-ttu-id="fede7-152">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="fede7-152">Turn on Microsoft Threat Protection</span></span>](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-threat-protection)
4. [<span data-ttu-id="fede7-153">設定 Office 365 的高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="fede7-153">Configure Office 365 Advanced Threat Protection</span></span>](deploy-threat-protection-configure.md#step-4-configure-office-365-advanced-threat-protection)
5. [<span data-ttu-id="fede7-154">設定 Microsoft Defender 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="fede7-154">Configure Microsoft Defender Advanced Threat Protection</span></span>](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [<span data-ttu-id="fede7-155">設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fede7-155">Configure Microsoft Cloud App Security</span></span>](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [<span data-ttu-id="fede7-156">監視狀態並採取動作</span><span class="sxs-lookup"><span data-stu-id="fede7-156">Monitor status and take actions</span></span>](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [<span data-ttu-id="fede7-157">訓練使用者</span><span class="sxs-lookup"><span data-stu-id="fede7-157">Train users</span></span>](deploy-threat-protection-configure.md#step-8-train-users)

<span data-ttu-id="fede7-158">您可以平行設定威脅防護功能，因此，如果您有多個安全小組負責不同的服務，他們就可以同時設定組織的保護功能。</span><span class="sxs-lookup"><span data-stu-id="fede7-158">Your threat protection features can be configured in parallel, so if you have multiple security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span> <span data-ttu-id="fede7-159">下圖說明部署威脅防護功能的高層級流程。</span><span class="sxs-lookup"><span data-stu-id="fede7-159">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![部署威脅防護功能的程式](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


