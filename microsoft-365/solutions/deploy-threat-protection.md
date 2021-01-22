---
title: 在 Microsoft 365 部署網路安全性威脅防護
description: 瞭解如何在 Microsoft 365 E5 部署威脅防護服務和 IT 網路安全性功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 79352aca2012e6615f41b19f4a77fc5cf125f4c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926747"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a><span data-ttu-id="e8954-103">在 Microsoft 365 部署威脅防護功能</span><span class="sxs-lookup"><span data-stu-id="e8954-103">Deploy threat protection capabilities across Microsoft 365</span></span>

<span data-ttu-id="e8954-104">[惡意](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)攻擊和複雜的網路攻擊 ，例如無檔案[](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)威脅，都是很常見的情況。</span><span class="sxs-lookup"><span data-stu-id="e8954-104">[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="e8954-105">企業需要以有效的 IT 網路安全性功能來保護本身和客戶。</span><span class="sxs-lookup"><span data-stu-id="e8954-105">Businesses need to protect themselves and their customers with effective IT network security capabilities.</span></span> <span data-ttu-id="e8954-106">這類攻擊可能會為貴組織造成重大問題，包括失去信任、財務問題、業務中斷等等。</span><span class="sxs-lookup"><span data-stu-id="e8954-106">Such attacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="e8954-107">防範威脅很重要，但可能難以判斷要專注于貴組織的時間、精力和資源。</span><span class="sxs-lookup"><span data-stu-id="e8954-107">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> 

<span data-ttu-id="e8954-108">我們產品與服務內建 Microsoft 安全性解決方案。</span><span class="sxs-lookup"><span data-stu-id="e8954-108">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="e8954-109">自動化與機器學習功能可以減少您安全性小組的負載，以確保已處理正確的專案。</span><span class="sxs-lookup"><span data-stu-id="e8954-109">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="e8954-110">而 Microsoft 網路安全性解決方案的強大功能，也建立在我們每天處理之智慧型安全性 Graph 的 [訊號上](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)。</span><span class="sxs-lookup"><span data-stu-id="e8954-110">And the strength of Microsoft network security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph).</span></span> <span data-ttu-id="e8954-111">Microsoft 365 安全性解決方案包括 [Microsoft 365 Defender，](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)這是一種能結合電子郵件、資料、裝置和身分身分之訊號的解決方案，以描繪貴組織的進層威脅圖片。</span><span class="sxs-lookup"><span data-stu-id="e8954-111">Microsoft 365 security solutions include [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), a solution that brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>


<span data-ttu-id="e8954-112">觀看這段影片以獲取部署程序概觀。</span><span class="sxs-lookup"><span data-stu-id="e8954-112">Watch this video for an overview of the deployment process.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

<span data-ttu-id="e8954-113">使用這篇文章做為執行威脅防護解決方案的指南。</span><span class="sxs-lookup"><span data-stu-id="e8954-113">Use this article as a guide for implementing your threat protection solution.</span></span>

## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="e8954-114">Microsoft 365 E5 中的威脅防護</span><span class="sxs-lookup"><span data-stu-id="e8954-114">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="e8954-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 可讓您使用自適性、內建智慧來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="e8954-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="e8954-116">使用 Microsoft 365 E5 中的威脅防護功能，您可以偵測並調查內部部署和雲端環境中進一步威脅、身分識別遭到入侵和惡意動作。</span><span class="sxs-lookup"><span data-stu-id="e8954-116">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="e8954-117">在 Microsoft 365 E5 中，威脅防護功能預設為整合。</span><span class="sxs-lookup"><span data-stu-id="e8954-117">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="e8954-118">每個功能發出的訊號，都為偵測和回應威脅的整體能力增加強度。</span><span class="sxs-lookup"><span data-stu-id="e8954-118">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="e8954-119">相較于非 Microsoft 產品，結合一組功能可為組織 、特別是多國組織提供最佳的保護。</span><span class="sxs-lookup"><span data-stu-id="e8954-119">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="e8954-120">下列影像說明本文所述的 Microsoft 365 E5 威脅防護服務和功能。</span><span class="sxs-lookup"><span data-stu-id="e8954-120">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 365 Defender 概觀](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="e8954-122">部署任一 Office 365 的 Defender 功能後，您即可以開啟 Microsoft 365 Defender，將訊號和資料放在同一個地方。</span><span class="sxs-lookup"><span data-stu-id="e8954-122">As soon as you deploy any of the Defender for Office 365 capabilities, you can turn on Microsoft 365 Defender, which brings the signals and data together into one place.</span></span> 

![Microsoft 365 Defender 儀表板的概念性圖例](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

<span data-ttu-id="e8954-124">下圖說明部署這些個別功能的建議路徑。</span><span class="sxs-lookup"><span data-stu-id="e8954-124">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

![M365 威脅防護訊號](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|<span data-ttu-id="e8954-126">解決方案/功能</span><span class="sxs-lookup"><span data-stu-id="e8954-126">Solution/capabilities</span></span>  |<span data-ttu-id="e8954-127">說明</span><span class="sxs-lookup"><span data-stu-id="e8954-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e8954-128">多重要素驗證和條件式存取</span><span class="sxs-lookup"><span data-stu-id="e8954-128">Multi-factor authentication and conditional access</span></span>     |<span data-ttu-id="e8954-129">防範身分和裝置遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="e8954-129">Protect against compromised identities and devices.</span></span> <span data-ttu-id="e8954-130">首先進行這項保護，因為這是基礎。</span><span class="sxs-lookup"><span data-stu-id="e8954-130">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="e8954-131">此指引中建議的組配置包括 Azure AD 身分識別保護做為先決條件。</span><span class="sxs-lookup"><span data-stu-id="e8954-131">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="e8954-132">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8954-132">Microsoft Defender for Identity</span></span>     |  <span data-ttu-id="e8954-133">雲端式安全性解決方案，利用您的內部部署 Active Directory 訊號來識別、偵測和調查進一步威脅、身分識別已遭到入侵，以及針對貴組織所導向的惡意 Insider 動作。</span><span class="sxs-lookup"><span data-stu-id="e8954-133">A cloud-based security solution that leverages your on-premises Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="e8954-134">接下來請專注于 Microsoft Defender 的身分識別，因為它能保護您的 On-prem 和雲端基礎結構、沒有相依性或先決條件，而且可以立即提供好處。</span><span class="sxs-lookup"><span data-stu-id="e8954-134">Focus on Microsoft Defender for Identity next because it protects your on-prem and your cloud infrastructure, has no dependencies or prerequisites, and can provide immediate benefit.</span></span>       | 
|<span data-ttu-id="e8954-135">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8954-135">Microsoft Defender for Office 365</span></span>     | <span data-ttu-id="e8954-136">保護貴組織免受電子郵件訊息、連結和 URL (和) 所造成的惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="e8954-136">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="e8954-137">惡意攻擊、網路釣魚、詐騙及其他攻擊類型的保護。</span><span class="sxs-lookup"><span data-stu-id="e8954-137">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="e8954-138">我們接下來建議使用設定 Office 365 的 Microsoft Defender，因為變更控制、從系統移移設定及其他考慮可能需要較長的時間部署。</span><span class="sxs-lookup"><span data-stu-id="e8954-138">Configuring Microsoft Defender for Office 365 is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <br><br><span data-ttu-id="e8954-139">注意：請務必設定 Exchange Online Protection 的所有 Office 365 訂閱 (威脅防護) 。</span><span class="sxs-lookup"><span data-stu-id="e8954-139">Note: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="e8954-140">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8954-140">Microsoft Defender for Endpoint</span></span>    | <span data-ttu-id="e8954-141">可協助防範、偵測、調查及回應進一步威脅的端點保護平臺。</span><span class="sxs-lookup"><span data-stu-id="e8954-141">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span>  <span data-ttu-id="e8954-142">端點的 Defender 可能需要一些時間進行部署，但可以與其他功能同時進行組組。</span><span class="sxs-lookup"><span data-stu-id="e8954-142">Defender for Endpoint can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="e8954-143">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e8954-143">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="e8954-144">探索、調查及監管的雲端存取安全性工作。</span><span class="sxs-lookup"><span data-stu-id="e8954-144">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="e8954-145">您可以提早啟用 Microsoft Cloud App 安全性，以開始收集資料和深入見解。</span><span class="sxs-lookup"><span data-stu-id="e8954-145">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="e8954-146">在 SaaS App 中執行資訊和其他目標保護需要規劃，而且可能會花上更多時間。</span><span class="sxs-lookup"><span data-stu-id="e8954-146">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="e8954-147">擁有多個安全小組的組織可以同時執行這些功能。</span><span class="sxs-lookup"><span data-stu-id="e8954-147">Organizations with multiple security teams can implement these capabilities in parallel.</span></span>

## <a name="deploy-your-threat-protection-solution"></a><span data-ttu-id="e8954-148">部署您的威脅防護解決方案</span><span class="sxs-lookup"><span data-stu-id="e8954-148">Deploy your threat protection solution</span></span>

<span data-ttu-id="e8954-149">若要確保貴組織有最佳的保護能力，請設定及部署您的安全性解決方案，以包含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e8954-149">To make sure your organization has the best protection possible, set up and deploy your security solution to include the following steps:</span></span>

1. [<span data-ttu-id="e8954-150">設定多重要素驗證和條件式存取策略</span><span class="sxs-lookup"><span data-stu-id="e8954-150">Set up multi-factor authentication and conditional access policies</span></span>](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [<span data-ttu-id="e8954-151">設定 Microsoft Defender 的身分識別</span><span class="sxs-lookup"><span data-stu-id="e8954-151">Configure Microsoft Defender for Identity</span></span>](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [<span data-ttu-id="e8954-152">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8954-152">Turn on Microsoft 365 Defender</span></span>](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [<span data-ttu-id="e8954-153">設定 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="e8954-153">Configure Defender for Office 365</span></span>](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [<span data-ttu-id="e8954-154">設定 Microsoft Defender 端點</span><span class="sxs-lookup"><span data-stu-id="e8954-154">Configure Microsoft Defender for Endpoint</span></span>](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [<span data-ttu-id="e8954-155">設定 Microsoft Cloud App 安全性</span><span class="sxs-lookup"><span data-stu-id="e8954-155">Configure Microsoft Cloud App Security</span></span>](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [<span data-ttu-id="e8954-156">監控狀態並採取行動</span><span class="sxs-lookup"><span data-stu-id="e8954-156">Monitor status and take actions</span></span>](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [<span data-ttu-id="e8954-157">訓練使用者</span><span class="sxs-lookup"><span data-stu-id="e8954-157">Train users</span></span>](deploy-threat-protection-configure.md#step-8-train-users)

<span data-ttu-id="e8954-158">您可以同時設定您的威脅防護功能，因此如果您有多個負責不同服務的網路安全小組，他們可以同時設定貴組織的防護功能。</span><span class="sxs-lookup"><span data-stu-id="e8954-158">Your threat protection features can be configured in parallel, so if you have multiple network security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span> <span data-ttu-id="e8954-159">下圖說明部署威脅防護功能的高層級程式。</span><span class="sxs-lookup"><span data-stu-id="e8954-159">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![部署威脅防護功能的流程](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
