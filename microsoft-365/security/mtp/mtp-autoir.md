---
title: Microsoft 威脅防護的自動化調查及回應
description: 深入瞭解 Microsoft 威脅防護中的自動化調查和回應功能（也稱為自我修復）
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
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2131af5e35aa0cf9f236940d2b4aaa2bed85190a
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199778"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a><span data-ttu-id="3667e-104">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="3667e-104">Automated investigation and response in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3667e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3667e-105">**Applies to:**</span></span>
- <span data-ttu-id="3667e-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="3667e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3667e-107">在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="3667e-107">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="3667e-108">優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。</span><span class="sxs-lookup"><span data-stu-id="3667e-108">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="3667e-109">安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="3667e-109">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="3667e-110">在 Microsoft 威脅防護中，利用自我修復的自動化調查和回應功能可能會有所説明。</span><span class="sxs-lookup"><span data-stu-id="3667e-110">Automated investigation and response capabilities, with self-healing, in Microsoft Threat Protection can help.</span></span>

<span data-ttu-id="3667e-111">請觀看下列影片，瞭解自我修復的運作方式：</span><span class="sxs-lookup"><span data-stu-id="3667e-111">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="3667e-112">在 Microsoft 威脅防護中，使用自我修復功能的自動化調查和回應可在您的裝置、電子郵件 & 內容和身分識別之間運作。</span><span class="sxs-lookup"><span data-stu-id="3667e-112">In Microsoft Threat Protection, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span> <span data-ttu-id="3667e-113">Microsoft 威脅防護將功能彙集在一起：</span><span class="sxs-lookup"><span data-stu-id="3667e-113">Microsoft Threat Protection brings together capabilities from:</span></span> 
- [<span data-ttu-id="3667e-114">Microsoft Defender 高級威脅防護中的自動化調查和修復</span><span class="sxs-lookup"><span data-stu-id="3667e-114">Automated investigation and remediation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="3667e-115">Office 365 高級威脅防護中的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="3667e-115">Automated investigation and response in Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="3667e-116">Azure 高級威脅偵測</span><span class="sxs-lookup"><span data-stu-id="3667e-116">Azure advanced threat detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [<span data-ttu-id="3667e-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3667e-117">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
<span data-ttu-id="3667e-118">本文說明自動化調查和回應的運作方式。</span><span class="sxs-lookup"><span data-stu-id="3667e-118">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="3667e-119">若要設定這些功能，請參閱 [在 Microsoft 威脅防護中設定自動化調查和回應功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="3667e-119">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-virtual-analyst"></a><span data-ttu-id="3667e-120">您的虛擬分析員</span><span class="sxs-lookup"><span data-stu-id="3667e-120">Your virtual analyst</span></span>

<span data-ttu-id="3667e-121">想像您的第 1 層 / 第 2 層安全性作業小組中有一個虛擬分析員。</span><span class="sxs-lookup"><span data-stu-id="3667e-121">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="3667e-122">虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。</span><span class="sxs-lookup"><span data-stu-id="3667e-122">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="3667e-123">虛擬助理可以全天候工作、提供無限能力，以及接受大量調查和威脅補救。</span><span class="sxs-lookup"><span data-stu-id="3667e-123">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="3667e-124">如此一來，虛擬助理可以大幅減少回應時間，讓您的安全性作業小組能夠進行其他重要的策略專案。</span><span class="sxs-lookup"><span data-stu-id="3667e-124">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="3667e-125">如果此案例好像是科學 fiction，就不是！</span><span class="sxs-lookup"><span data-stu-id="3667e-125">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="3667e-126">這類虛擬分析員是 Microsoft 威脅防護套件的一部分，其名稱是 *自動調查和回應*。</span><span class="sxs-lookup"><span data-stu-id="3667e-126">Such a virtual analyst is part of your Microsoft Threat Protection suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="3667e-127">自動化調查和回應可讓您的安全性運作小組大幅增加組織的容量，以處理安全性警示和事件。</span><span class="sxs-lookup"><span data-stu-id="3667e-127">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="3667e-128">透過自動化調查和回應，您可以減少處理調查和修復活動的成本，並充分利用威脅防護套件。</span><span class="sxs-lookup"><span data-stu-id="3667e-128">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="3667e-129">自動化調查和回應可協助您進行安全性運作小組：</span><span class="sxs-lookup"><span data-stu-id="3667e-129">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="3667e-130">判斷是否要針對威脅採取動作；</span><span class="sxs-lookup"><span data-stu-id="3667e-130">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="3667e-131">執行 (或建議) 任何必要補救動作；</span><span class="sxs-lookup"><span data-stu-id="3667e-131">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="3667e-132">判斷應該要進行哪些其他調查；以及</span><span class="sxs-lookup"><span data-stu-id="3667e-132">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="3667e-133">針對其他警示重複採取必要程序。</span><span class="sxs-lookup"><span data-stu-id="3667e-133">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="3667e-134">自動化調查程序</span><span class="sxs-lookup"><span data-stu-id="3667e-134">The automated investigation process</span></span>

<span data-ttu-id="3667e-135">**警示** > **事件** > **自動化調查** > **結果** > **補救動作**</span><span class="sxs-lookup"><span data-stu-id="3667e-135">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="3667e-136">觸發的警示會建立事件，以開始自動調查。</span><span class="sxs-lookup"><span data-stu-id="3667e-136">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="3667e-137">該調查會產生一或多個補救動作。</span><span class="sxs-lookup"><span data-stu-id="3667e-137">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="3667e-138">在 Microsoft 威脅防護中，每個自動化調查會與 Azure 進階威脅防護 (Azure ATP)、Microsoft Defender 進階威脅防護 (Microsoft Defender ATP) 和 Office 365 進階威脅防護 (Office 365 ATP) 的訊號有關聯，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="3667e-138">In Microsoft Threat Protection, each automated investigation correlates signals across Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP), and Office 365 Advanced Threat Protection (Office 365 ATP), as summarized in the following table:</span></span> 

|<span data-ttu-id="3667e-139">實體</span><span class="sxs-lookup"><span data-stu-id="3667e-139">Entities</span></span> |<span data-ttu-id="3667e-140">威脅防護服務</span><span class="sxs-lookup"><span data-stu-id="3667e-140">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="3667e-141">裝置 (也稱為端點)</span><span class="sxs-lookup"><span data-stu-id="3667e-141">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="3667e-142">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3667e-142">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="3667e-143">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="3667e-143">Azure ATP</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="3667e-144">電子郵件內容 (信箱中的檔案和郵件)</span><span class="sxs-lookup"><span data-stu-id="3667e-144">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="3667e-145">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="3667e-145">Office 365 ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="3667e-146">每一項調查都會產生 verdicts (*惡意*、 *可疑*或 *沒有威脅*) 針對每個證據調查的部分。</span><span class="sxs-lookup"><span data-stu-id="3667e-146">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="3667e-147">根據威脅類型和產生的判定，您的組織的安全性運作小組會自動或核准執行修正動作。</span><span class="sxs-lookup"><span data-stu-id="3667e-147">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="3667e-148">待處理和已完成的操作會列在[重要訊息中心](mtp-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3667e-148">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="3667e-149">當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。</span><span class="sxs-lookup"><span data-stu-id="3667e-149">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="3667e-150">如果在其他地方看到受感染的實體，則自動化調查將擴大其範圍，以包括該實體，並且將執行一般安全性劇本。</span><span class="sxs-lookup"><span data-stu-id="3667e-150">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="3667e-151">並非每個提醒都會觸發自動調查，而並非每項調查都會產生自動修復動作。這全都取決於組織如何設定自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="3667e-151">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="3667e-152">請參閱 [設定 Microsoft 威脅防護中的自動化調查和回應功能](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="3667e-152">See [Configure automated investigation and response capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="3667e-153">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3667e-153">Next steps</span></span>

- [<span data-ttu-id="3667e-154">請參閱 Microsoft 威脅防護中的自動化調查和回應必要條件</span><span class="sxs-lookup"><span data-stu-id="3667e-154">See the prerequisites for automated investigation and response in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [<span data-ttu-id="3667e-155">為您的組織設定自動調查和回應</span><span class="sxs-lookup"><span data-stu-id="3667e-155">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="3667e-156">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="3667e-156">Learn more about the Action center</span></span>](mtp-action-center.md)
