---
title: 為第一個事件準備安全性狀況
description: 針對 Microsoft 365 Defender 中的第一個事件，設定 Microsoft 365 租使用者的安全性狀況。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: da9147955c5da9ea727854420b3d4d160583ef73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840931"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="da70e-104">為第一個事件準備安全性狀況</span><span class="sxs-lookup"><span data-stu-id="da70e-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="da70e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="da70e-105">**Applies to:**</span></span>
- <span data-ttu-id="da70e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da70e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="da70e-107">為事件處理做好準備時，應從不同類型的安全性事件中，設定組織網路的足夠保護。</span><span class="sxs-lookup"><span data-stu-id="da70e-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="da70e-108">若要降低安全性事件的風險，國家標準和技術協會 (NIST) 建議多種安全性作法，包括風險評估、強化主機安全性、安全地設定網路，以及防止惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="da70e-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="da70e-109">Microsoft 365Defender 可協助您解決事件防護的幾個層面：</span><span class="sxs-lookup"><span data-stu-id="da70e-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="da70e-110">實施 [零信任](/security/zero-trust/) 架構</span><span class="sxs-lookup"><span data-stu-id="da70e-110">Implementing a [Zero Trust](/security/zero-trust/) framework</span></span>
- <span data-ttu-id="da70e-111">使用[Microsoft 安全分數](microsoft-secure-score.md)指派分數來判斷您的安全性狀況</span><span class="sxs-lookup"><span data-stu-id="da70e-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="da70e-112">透過[威脅和弱點管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)中的漏洞評估來防止威脅</span><span class="sxs-lookup"><span data-stu-id="da70e-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="da70e-113">瞭解最新的安全性威脅，以做好準備</span><span class="sxs-lookup"><span data-stu-id="da70e-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="da70e-114">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="da70e-114">Step 1.</span></span> <span data-ttu-id="da70e-115">實現零信任</span><span class="sxs-lookup"><span data-stu-id="da70e-115">Implement Zero Trust</span></span>

<span data-ttu-id="da70e-116">「[零信任](/security/zero-trust/)」是整合的安全性理念和端對端策略，可考慮任何現代環境的複雜性質，包括行動工作力和使用者、裝置、應用程式及資料（可能位於何處）。</span><span class="sxs-lookup"><span data-stu-id="da70e-116">[Zero Trust](/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="da70e-117">透過提供單一的玻璃窗格，以一致的方式管理所有的偵測，Microsoft 365 Defender 可讓安全性作業小組輕鬆地執行零信任的[指導原則](/security/zero-trust/#guiding-principles-of-zero-trust)。</span><span class="sxs-lookup"><span data-stu-id="da70e-117">By providing a single pane of glass to manage all detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="da70e-118">Microsoft 365 的元件會顯示已執行之規則的破壞，該規則會將 Microsoft Defender for Endpoint (MDE) 或其他行動安全性廠商整合為資訊來源，以針對裝置合規性原則和裝置型條件式存取原則的資訊來源，以建立零信任的條件存取原則。</span><span class="sxs-lookup"><span data-stu-id="da70e-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="da70e-119">裝置風險會直接影響該裝置的使用者可存取的資源。</span><span class="sxs-lookup"><span data-stu-id="da70e-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="da70e-120">根據特定準則，「拒絕存取資源」是零信任和 Microsoft 365 Defender 的主要主題，提供判斷信任層級準則所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="da70e-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="da70e-121">例如，Microsoft 365 Defender 可透過威脅和弱點管理頁面提供裝置的軟體版本層級，而條件式存取原則會限制具有過時或易受攻擊版本的裝置。</span><span class="sxs-lookup"><span data-stu-id="da70e-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="da70e-122">「自動化」是實施及維護零信任環境的重要部分，同時也減少了可能會造成事件回應 (紅外) 事件的警示數目。</span><span class="sxs-lookup"><span data-stu-id="da70e-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="da70e-123">Microsoft 365 Defender 的元件可以是自動化的，例如，[修正動作](m365d-autoir.md) (稱為 Microsoft 365 安全性中心) 的事件調查、通知動作，甚至是在[ServiceNow](https://microsoft.service-now.com/sp/)中建立支援票證。</span><span class="sxs-lookup"><span data-stu-id="da70e-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="da70e-124">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="da70e-124">Step 2.</span></span> <span data-ttu-id="da70e-125">決定組織的安全性狀況</span><span class="sxs-lookup"><span data-stu-id="da70e-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="da70e-126">接下來，組織可以在 Microsoft 365 Defender 中使用[Microsoft 安全評分](microsoft-secure-score.md)，以判斷您目前的安全性狀況，並考慮改進的建議。</span><span class="sxs-lookup"><span data-stu-id="da70e-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="da70e-127">分數越高，組織採取的安全性建議和改善動作就越好。</span><span class="sxs-lookup"><span data-stu-id="da70e-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="da70e-128">安全分數建議可跨不同的產品進行，並可讓組織提升其分數甚至更高。</span><span class="sxs-lookup"><span data-stu-id="da70e-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft security center 中 Microsoft Secure 得分的範例":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="da70e-130">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="da70e-130">Step 3.</span></span> <span data-ttu-id="da70e-131">評估貴組織的弱點洩密</span><span class="sxs-lookup"><span data-stu-id="da70e-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="da70e-132">防止事件可以協助簡化安全性作業，以著重于不斷進行重要及重要的安全性事件。</span><span class="sxs-lookup"><span data-stu-id="da70e-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="da70e-133">軟體弱點通常是攻擊的 preventable 進入點，可導致資料竊取、資料遺失或商務運作中斷。</span><span class="sxs-lookup"><span data-stu-id="da70e-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="da70e-134">如果不進行任何攻擊，安全性作業必須盡力達成並維護組織中可接受的 [漏洞公開](../defender-endpoint/tvm-exposure-score.md) 等級。</span><span class="sxs-lookup"><span data-stu-id="da70e-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="da70e-135">若要檢查您的軟體修補進度，請造訪您可以從 Microsoft 365 defender 透過 [**其他資源**] 索引標籤存取的 Endpoint for Endpoint 中的 [威脅和弱點管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)頁面。</span><span class="sxs-lookup"><span data-stu-id="da70e-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft security center 中威脅和弱點頁面的範例"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="da70e-137">4. 瞭解新興威脅</span><span class="sxs-lookup"><span data-stu-id="da70e-137">4. Understand emerging threats</span></span>

<span data-ttu-id="da70e-138">在 Microsoft 365 的安全性中心使用[威脅分析](threat-analytics.md)，以維持目前安全性威脅環境的最新狀態。</span><span class="sxs-lookup"><span data-stu-id="da70e-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="da70e-139">專家 Microsoft 安全性調查程式會建立報告，以詳細描述最新的網路威脅，讓您瞭解它們對 Microsoft 365 訂閱、裝置和使用者有何影響。</span><span class="sxs-lookup"><span data-stu-id="da70e-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="da70e-140">這些報告可以包含：</span><span class="sxs-lookup"><span data-stu-id="da70e-140">These reports can include:</span></span>

- <span data-ttu-id="da70e-141">作用中的威脅演員及其活動</span><span class="sxs-lookup"><span data-stu-id="da70e-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="da70e-142">常見和新的攻擊技術</span><span class="sxs-lookup"><span data-stu-id="da70e-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="da70e-143">嚴重弱點</span><span class="sxs-lookup"><span data-stu-id="da70e-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="da70e-144">常見的攻擊面</span><span class="sxs-lookup"><span data-stu-id="da70e-144">Common attack surfaces</span></span>
- <span data-ttu-id="da70e-145">流行惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="da70e-145">Prevalent malware</span></span>

<span data-ttu-id="da70e-146">「威脅分析」也會查看您的設定和警示，以判斷您所在的風險以及是否有適用于報告的活動警示。</span><span class="sxs-lookup"><span data-stu-id="da70e-146">Threat analytics also looks at your configuration and alerts to determine how at-risk you are and if there are active alerts applicable to a report.</span></span>

<span data-ttu-id="da70e-147">您可以執行新興威脅的建議，以加強安全性狀況，並將攻擊面降至最低。</span><span class="sxs-lookup"><span data-stu-id="da70e-147">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="da70e-148">在排程中的時間，定期檢查 Microsoft 365 安全性中心的 [[威脅分析](threat-analytics.md)] 區段。</span><span class="sxs-lookup"><span data-stu-id="da70e-148">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="da70e-149">下一步</span><span class="sxs-lookup"><span data-stu-id="da70e-149">Next step</span></span>

<span data-ttu-id="da70e-150">[![步驟1：瞭解如何會審和分析事件](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="da70e-150">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="da70e-151">瞭解如何 [會審和分析事件](first-incident-analyze.md)。</span><span class="sxs-lookup"><span data-stu-id="da70e-151">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da70e-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="da70e-152">See also</span></span>

- [<span data-ttu-id="da70e-153">事件概觀</span><span class="sxs-lookup"><span data-stu-id="da70e-153">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="da70e-154">調查事件</span><span class="sxs-lookup"><span data-stu-id="da70e-154">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="da70e-155">管理事件</span><span class="sxs-lookup"><span data-stu-id="da70e-155">Manage incidents</span></span>](manage-incidents.md)
