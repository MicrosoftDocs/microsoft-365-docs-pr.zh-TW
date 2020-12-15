---
title: Microsoft 365 Defender 的自動化調查和回應
description: 深入瞭解 Microsoft 365 Defender 中的自動化調查和回應功能（也稱為自我修復）
keywords: 自動化，調查，警示，觸發器，動作，修正，自我修復
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7c28b7f3ac797f7402cfdb1f604fcef1e142a31b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683304"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="ee02b-104">Microsoft 365 Defender 的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="ee02b-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ee02b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ee02b-105">**Applies to:**</span></span>
- <span data-ttu-id="ee02b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee02b-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="ee02b-107">想要體驗 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="ee02b-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="ee02b-108">您可以 [在實驗室環境中進行評估](https://aka.ms/mtp-trial-lab) ，或 [在實際執行中執行您的試驗專案](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="ee02b-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="ee02b-109">自動化調查及自我修復的運作方式</span><span class="sxs-lookup"><span data-stu-id="ee02b-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="ee02b-110">在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="ee02b-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="ee02b-111">優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。</span><span class="sxs-lookup"><span data-stu-id="ee02b-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="ee02b-112">安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="ee02b-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="ee02b-113">Microsoft 365 Defender 中的自動調查和回應功能（透過自我修復）可能會有所説明。</span><span class="sxs-lookup"><span data-stu-id="ee02b-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="ee02b-114">請觀看下列影片，瞭解自我修復的運作方式：</span><span class="sxs-lookup"><span data-stu-id="ee02b-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="ee02b-115">在 Microsoft 365 Defender 中，使用自我修復功能的自動化調查和回應可在您的裝置、電子郵件 & 內容和身分識別之間運作。</span><span class="sxs-lookup"><span data-stu-id="ee02b-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="ee02b-116">本文說明自動化調查和回應的運作方式。</span><span class="sxs-lookup"><span data-stu-id="ee02b-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="ee02b-117">若要設定這些功能，請參閱 [在 Microsoft 365 Defender 中設定自動調查和回應功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="ee02b-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="ee02b-118">您自己的虛擬分析員</span><span class="sxs-lookup"><span data-stu-id="ee02b-118">Your own virtual analyst</span></span>

<span data-ttu-id="ee02b-119">想像您的第 1 層 / 第 2 層安全性作業小組中有一個虛擬分析員。</span><span class="sxs-lookup"><span data-stu-id="ee02b-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="ee02b-120">虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。</span><span class="sxs-lookup"><span data-stu-id="ee02b-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="ee02b-121">虛擬助理可以全天候工作、提供無限能力，以及接受大量調查和威脅補救。</span><span class="sxs-lookup"><span data-stu-id="ee02b-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="ee02b-122">如此一來，虛擬助理可以大幅減少回應時間，讓您的安全性作業小組能夠進行其他重要的策略專案。</span><span class="sxs-lookup"><span data-stu-id="ee02b-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="ee02b-123">如果此案例好像是科學 fiction，就不是！</span><span class="sxs-lookup"><span data-stu-id="ee02b-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="ee02b-124">這類虛擬分析員是 Microsoft 365 Defender 套件的一部分，而且其名稱是 *自動調查和回應*。</span><span class="sxs-lookup"><span data-stu-id="ee02b-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="ee02b-125">自動化調查和回應可讓您的安全性運作小組大幅增加組織的容量，以處理安全性警示和事件。</span><span class="sxs-lookup"><span data-stu-id="ee02b-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="ee02b-126">透過自動化調查和回應，您可以減少處理調查和修復活動的成本，並充分利用威脅防護套件。</span><span class="sxs-lookup"><span data-stu-id="ee02b-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="ee02b-127">自動化調查和回應可協助您進行安全性運作小組：</span><span class="sxs-lookup"><span data-stu-id="ee02b-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="ee02b-128">判斷是否要針對威脅採取動作；</span><span class="sxs-lookup"><span data-stu-id="ee02b-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="ee02b-129">執行 (或建議) 任何必要補救動作；</span><span class="sxs-lookup"><span data-stu-id="ee02b-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="ee02b-130">判斷應該要進行哪些其他調查；以及</span><span class="sxs-lookup"><span data-stu-id="ee02b-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="ee02b-131">針對其他警示重複採取必要程序。</span><span class="sxs-lookup"><span data-stu-id="ee02b-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="ee02b-132">自動化調查程序</span><span class="sxs-lookup"><span data-stu-id="ee02b-132">The automated investigation process</span></span>

<span data-ttu-id="ee02b-133">**警示** > **事件** > **自動化調查** > **結果** > **補救動作**</span><span class="sxs-lookup"><span data-stu-id="ee02b-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="ee02b-134">觸發的警示會建立事件，以開始自動調查。</span><span class="sxs-lookup"><span data-stu-id="ee02b-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="ee02b-135">該調查會產生一或多個補救動作。</span><span class="sxs-lookup"><span data-stu-id="ee02b-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="ee02b-136">在 Microsoft 365 Defender 中，每個自動調查都會針對所有 Microsoft Defender 身分識別、Microsoft Defender for Endpoint 和 Defender for Office 365 進行相互關聯的信號，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="ee02b-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="ee02b-137">實體</span><span class="sxs-lookup"><span data-stu-id="ee02b-137">Entities</span></span> |<span data-ttu-id="ee02b-138">威脅防護服務</span><span class="sxs-lookup"><span data-stu-id="ee02b-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="ee02b-139">裝置 (也稱為端點)</span><span class="sxs-lookup"><span data-stu-id="ee02b-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="ee02b-140">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ee02b-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="ee02b-141">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ee02b-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="ee02b-142">電子郵件內容 (信箱中的檔案和郵件)</span><span class="sxs-lookup"><span data-stu-id="ee02b-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="ee02b-143">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ee02b-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="ee02b-144">每一項調查都會產生 verdicts (*惡意*、 *可疑* 或 *沒有威脅*) 針對每個證據調查的部分。</span><span class="sxs-lookup"><span data-stu-id="ee02b-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="ee02b-145">根據威脅類型和產生的判定，您的組織的安全性運作小組會自動或核准執行修正動作。</span><span class="sxs-lookup"><span data-stu-id="ee02b-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="ee02b-146">待處理和已完成的操作會列在[重要訊息中心](mtp-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ee02b-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="ee02b-147">當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。</span><span class="sxs-lookup"><span data-stu-id="ee02b-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="ee02b-148">如果在其他地方看到受感染的實體，則自動化調查將擴大其範圍，以包括該實體，並且將執行一般安全性劇本。</span><span class="sxs-lookup"><span data-stu-id="ee02b-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="ee02b-149">並非每個提醒都會觸發自動調查，而並非每項調查都會產生自動修復動作。這全都取決於組織如何設定自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="ee02b-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="ee02b-150">請參閱 [設定 Microsoft 365 Defender 中的自動化調查和回應功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="ee02b-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="ee02b-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ee02b-151">Next steps</span></span>

- [<span data-ttu-id="ee02b-152">請參閱 Microsoft 365 Defender 的自動化調查和回應必要條件</span><span class="sxs-lookup"><span data-stu-id="ee02b-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="ee02b-153">為您的組織設定自動調查和回應</span><span class="sxs-lookup"><span data-stu-id="ee02b-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="ee02b-154">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="ee02b-154">Learn more about the Action center</span></span>](mtp-action-center.md)
