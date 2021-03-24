---
title: Microsoft 365 Defender 的自動化調查和回應
description: 深入瞭解 Microsoft 365 Defender 中的自動化調查和回應功能（也稱為自我修復）
keywords: 自動化，調查，警示，觸發器，動作，修正，自我修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c12937c016875c26a7212117e41aac4349cb540d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059212"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="b9566-104">Microsoft 365 Defender 的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="b9566-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b9566-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b9566-105">**Applies to:**</span></span>
- <span data-ttu-id="b9566-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9566-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b9566-107">如果您的組織使用 [Microsoft 365 Defender](microsoft-365-defender.md)，當偵測到惡意或可疑的專案時，您的安全性作業小組會收到警示。</span><span class="sxs-lookup"><span data-stu-id="b9566-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert whenever a malicious or suspicious artifact is detected.</span></span> <span data-ttu-id="b9566-108">針對來自于的威脅看似永不終止的流程，安全性小組通常面臨著處理大量警示的挑戰。</span><span class="sxs-lookup"><span data-stu-id="b9566-108">Given the seemingly never-ending flow of threats that come in, security teams often face challenges in addressing the high volume of alerts.</span></span> <span data-ttu-id="b9566-109">幸運的是，Microsoft 365 Defender 包含自動調查和修正 (空氣) 功能，可協助您的安全性運作小組更有效率地處理威脅。</span><span class="sxs-lookup"><span data-stu-id="b9566-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="b9566-110">本文提供 AIR 的概述，並包含後續步驟和其他資源的連結。</span><span class="sxs-lookup"><span data-stu-id="b9566-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="b9566-111">想要體驗 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="b9566-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="b9566-112">您可以 [在實驗室環境中進行評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ，或 [在實際執行中執行您的試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="b9566-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="b9566-113">自動化調查及自我修復的運作方式</span><span class="sxs-lookup"><span data-stu-id="b9566-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="b9566-114">在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="b9566-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="b9566-115">優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。</span><span class="sxs-lookup"><span data-stu-id="b9566-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="b9566-116">安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="b9566-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="b9566-117">Microsoft 365 Defender 中的自動調查和回應功能（透過自我修復）可能會有所説明。</span><span class="sxs-lookup"><span data-stu-id="b9566-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="b9566-118">請觀看下列影片，瞭解自我修復的運作方式：</span><span class="sxs-lookup"><span data-stu-id="b9566-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="b9566-119">在 Microsoft 365 Defender 中，使用自我修復功能的自動化調查和回應可在您的裝置、電子郵件 & 內容和身分識別之間運作。</span><span class="sxs-lookup"><span data-stu-id="b9566-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="b9566-120">本文說明自動化調查和回應的運作方式。</span><span class="sxs-lookup"><span data-stu-id="b9566-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="b9566-121">若要設定這些功能，請參閱 [在 Microsoft 365 Defender 中設定自動調查和回應功能](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="b9566-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="b9566-122">您自己的虛擬分析員</span><span class="sxs-lookup"><span data-stu-id="b9566-122">Your own virtual analyst</span></span>

<span data-ttu-id="b9566-123">假設您在第1層或第2層安全性運作小組中有虛擬分析員。</span><span class="sxs-lookup"><span data-stu-id="b9566-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="b9566-124">虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。</span><span class="sxs-lookup"><span data-stu-id="b9566-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="b9566-125">虛擬助理可以全天候工作、提供無限能力，以及接受大量調查和威脅補救。</span><span class="sxs-lookup"><span data-stu-id="b9566-125">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="b9566-126">如此一來，虛擬助理可以大幅減少回應時間，讓您的安全性作業小組能夠進行其他重要的策略專案。</span><span class="sxs-lookup"><span data-stu-id="b9566-126">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="b9566-127">如果此案例好像是科學 fiction，就不是！</span><span class="sxs-lookup"><span data-stu-id="b9566-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="b9566-128">這類虛擬分析員是 Microsoft 365 Defender 套件的一部分，而且其名稱是 *自動調查和回應*。</span><span class="sxs-lookup"><span data-stu-id="b9566-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="b9566-129">自動化調查和回應功能可讓您的安全性運作小組大幅增加組織的容量，以處理安全性警示和事件。</span><span class="sxs-lookup"><span data-stu-id="b9566-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="b9566-130">透過自動化調查和回應，您可以減少處理調查和修復活動的成本，並充分利用威脅防護套件。</span><span class="sxs-lookup"><span data-stu-id="b9566-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="b9566-131">自動化調查和回應功能可協助您的安全性運作小組：</span><span class="sxs-lookup"><span data-stu-id="b9566-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="b9566-132">判斷是否要針對威脅採取動作；</span><span class="sxs-lookup"><span data-stu-id="b9566-132">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="b9566-133">採取 (或建議) 任何必要的修正動作;</span><span class="sxs-lookup"><span data-stu-id="b9566-133">Taking (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="b9566-134">決定是否要進行其他調查？和</span><span class="sxs-lookup"><span data-stu-id="b9566-134">Determining whether and what other investigations should occur; and</span></span>
4. <span data-ttu-id="b9566-135">針對其他警示重複採取必要程序。</span><span class="sxs-lookup"><span data-stu-id="b9566-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="b9566-136">自動化調查程序</span><span class="sxs-lookup"><span data-stu-id="b9566-136">The automated investigation process</span></span>

<span data-ttu-id="b9566-137">警示會建立事件，可開始自動調查。</span><span class="sxs-lookup"><span data-stu-id="b9566-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="b9566-138">自動調查會產生每個證據的判定。</span><span class="sxs-lookup"><span data-stu-id="b9566-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="b9566-139">Verdicts 可以是：</span><span class="sxs-lookup"><span data-stu-id="b9566-139">Verdicts can be:</span></span>
- <span data-ttu-id="b9566-140">*惡意*;</span><span class="sxs-lookup"><span data-stu-id="b9566-140">*Malicious*;</span></span>
- <span data-ttu-id="b9566-141">*可疑*;或</span><span class="sxs-lookup"><span data-stu-id="b9566-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="b9566-142">*找不到威脅*。</span><span class="sxs-lookup"><span data-stu-id="b9566-142">*No threats found*.</span></span> 

<span data-ttu-id="b9566-143">識別惡意或可疑實體的修復動作。</span><span class="sxs-lookup"><span data-stu-id="b9566-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="b9566-144">修正動作範例包括：</span><span class="sxs-lookup"><span data-stu-id="b9566-144">Examples of remediation actions include:</span></span>
- <span data-ttu-id="b9566-145">將檔案傳送至隔離區;</span><span class="sxs-lookup"><span data-stu-id="b9566-145">Sending a file to quarantine;</span></span>
- <span data-ttu-id="b9566-146">停止進程;</span><span class="sxs-lookup"><span data-stu-id="b9566-146">Stopping a process;</span></span>
- <span data-ttu-id="b9566-147">隔離裝置;</span><span class="sxs-lookup"><span data-stu-id="b9566-147">Isolating a device;</span></span>
- <span data-ttu-id="b9566-148">封鎖 URL;和</span><span class="sxs-lookup"><span data-stu-id="b9566-148">Blocking a URL; and</span></span> 
- <span data-ttu-id="b9566-149">其他動作。</span><span class="sxs-lookup"><span data-stu-id="b9566-149">other actions.</span></span> <span data-ttu-id="b9566-150"> (請參閱 [Microsoft 365 Defender 中的修復動作](m365d-remediation-actions.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="b9566-150">(See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).)</span></span>

<span data-ttu-id="b9566-151">根據您的組織 [設定自動化調查和回應功能的方式](m365d-configure-auto-investigation-response.md) ，修復動作會自動採取或僅在安全操作小組核准時進行。</span><span class="sxs-lookup"><span data-stu-id="b9566-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="b9566-152">所有動作（不論是擱置或已完成的動作）都會列在 [重要訊息 [中心](m365d-action-center.md)]。</span><span class="sxs-lookup"><span data-stu-id="b9566-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="b9566-153">當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。</span><span class="sxs-lookup"><span data-stu-id="b9566-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="b9566-154">如果有其他地方看到 incriminated 實體，則自動調查會將其範圍擴大為包含該實體，而調查程式會重複。</span><span class="sxs-lookup"><span data-stu-id="b9566-154">If an incriminated entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="b9566-155">在 Microsoft 365 Defender 中，每個自動調查都會針對所有 Microsoft Defender 身分識別、Microsoft Defender for Endpoint 和 Defender for Office 365 進行相互關聯的信號，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="b9566-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="b9566-156">實體</span><span class="sxs-lookup"><span data-stu-id="b9566-156">Entities</span></span> |<span data-ttu-id="b9566-157">威脅防護服務</span><span class="sxs-lookup"><span data-stu-id="b9566-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="b9566-158">裝置 (也稱為端點，有時也稱為機器) </span><span class="sxs-lookup"><span data-stu-id="b9566-158">Devices (also referred to as endpoints, and sometimes referred to as machines)</span></span>     |[<span data-ttu-id="b9566-159">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9566-159">Microsoft Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md)<br/>[<span data-ttu-id="b9566-160">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9566-160">Microsoft Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="b9566-161">電子郵件內容 (可以包含檔案和 URLs 的電子郵件) </span><span class="sxs-lookup"><span data-stu-id="b9566-161">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="b9566-162">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9566-162">Microsoft Defender for Office 365</span></span>](../defender-365-security/defender-for-office-365.md)         |

> [!NOTE]
> <span data-ttu-id="b9566-163">並非每個提醒都會觸發自動調查，而並非每項調查都會產生自動修復動作。這取決於組織如何設定自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="b9566-163">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; it depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="b9566-164">請參閱 [設定 Microsoft 365 Defender 中的自動化調查和回應功能](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="b9566-164">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9566-165">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b9566-165">Next steps</span></span>

- [<span data-ttu-id="b9566-166">請參閱 Microsoft 365 Defender 的自動化調查和回應必要條件</span><span class="sxs-lookup"><span data-stu-id="b9566-166">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="b9566-167">為您的組織設定自動調查和回應</span><span class="sxs-lookup"><span data-stu-id="b9566-167">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="b9566-168">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="b9566-168">Learn more about the Action center</span></span>](m365d-action-center.md)
