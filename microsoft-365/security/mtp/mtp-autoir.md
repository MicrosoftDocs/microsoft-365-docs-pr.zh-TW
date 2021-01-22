---
title: Microsoft 365 Defender 中的自動化調查與回應
description: 取得 Microsoft 365 Defender 中自動化調查與回應功能概觀 ，也稱為自我管理
keywords: 自動化、調查、警示、觸發、動作、補救、自我保護
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930327"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="b2c4c-104">Microsoft 365 Defender 中的自動化調查與回應</span><span class="sxs-lookup"><span data-stu-id="b2c4c-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b2c4c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b2c4c-105">**Applies to:**</span></span>
- <span data-ttu-id="b2c4c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2c4c-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="b2c4c-107">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b2c4c-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="b2c4c-108">您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="b2c4c-109">自動調查與自我保護如何運作</span><span class="sxs-lookup"><span data-stu-id="b2c4c-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="b2c4c-110">當安全性警訊觸發時，您的安全性作業小組會決定要調查這些警示，並採取行動來保護貴組織。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="b2c4c-111">優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="b2c4c-112">安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="b2c4c-113">Microsoft 365 Defender 中的自動調查及回應功能可協助進行自我調查。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="b2c4c-114">請觀看以下影片，瞭解自助運作方式：</span><span class="sxs-lookup"><span data-stu-id="b2c4c-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="b2c4c-115">在 Microsoft 365 Defender 中，具有自助功能的自動化調查與回應可運作于您的裝置、電子郵件&內容和身分身分。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="b2c4c-116">本文將說明自動化調查與回應如何運作。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="b2c4c-117">若要設定這些功能，請參閱 [Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)中的設定自動化調查與回應功能。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="b2c4c-118">您自己的虛擬分析師</span><span class="sxs-lookup"><span data-stu-id="b2c4c-118">Your own virtual analyst</span></span>

<span data-ttu-id="b2c4c-119">想像您的第 1 層 / 第 2 層安全性作業小組中有一個虛擬分析員。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="b2c4c-120">虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="b2c4c-121">虛擬助理可以全天候工作、提供無限能力，以及接受大量調查和威脅補救。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="b2c4c-122">如此一來，虛擬助理可以大幅減少回應時間，讓您的安全性作業小組能夠進行其他重要的策略專案。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="b2c4c-123">如果這個案例聽起來是科幻作品，那不一樣！</span><span class="sxs-lookup"><span data-stu-id="b2c4c-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="b2c4c-124">這樣的虛擬分析師是 Microsoft 365 Defender 套件的一部分，其名稱屬於 *自動化調查與回應。*</span><span class="sxs-lookup"><span data-stu-id="b2c4c-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="b2c4c-125">自動化調查與回應可讓安全性作業小組大幅提升貴組織處理安全性警訊和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="b2c4c-126">使用自動化調查與回應，您可以降低處理調查與補救活動的成本，並完全利用您的威脅防護套件。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="b2c4c-127">自動化調查及回應可協助您的安全性作業小組：</span><span class="sxs-lookup"><span data-stu-id="b2c4c-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="b2c4c-128">判斷是否要針對威脅採取動作；</span><span class="sxs-lookup"><span data-stu-id="b2c4c-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="b2c4c-129">執行 (或建議) 任何必要補救動作；</span><span class="sxs-lookup"><span data-stu-id="b2c4c-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="b2c4c-130">判斷應該要進行哪些其他調查；以及</span><span class="sxs-lookup"><span data-stu-id="b2c4c-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="b2c4c-131">針對其他警示重複採取必要程序。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="b2c4c-132">自動化調查程序</span><span class="sxs-lookup"><span data-stu-id="b2c4c-132">The automated investigation process</span></span>

<span data-ttu-id="b2c4c-133">**警示** > **事件** > **自動化調查** > **結果** > **補救動作**</span><span class="sxs-lookup"><span data-stu-id="b2c4c-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="b2c4c-134">觸發的警示會建立事件，可開始自動化調查。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="b2c4c-135">該調查會產生一或多個補救動作。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="b2c4c-136">在 Microsoft 365 Defender 中，每個自動化調查會關聯 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Defender for Office 365 的訊號，如下表摘要：</span><span class="sxs-lookup"><span data-stu-id="b2c4c-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="b2c4c-137">實體</span><span class="sxs-lookup"><span data-stu-id="b2c4c-137">Entities</span></span> |<span data-ttu-id="b2c4c-138">威脅防護服務</span><span class="sxs-lookup"><span data-stu-id="b2c4c-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="b2c4c-139">裝置 (也稱為端點)</span><span class="sxs-lookup"><span data-stu-id="b2c4c-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="b2c4c-140">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b2c4c-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="b2c4c-141">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b2c4c-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="b2c4c-142">電子郵件內容 (信箱中的檔案和郵件)</span><span class="sxs-lookup"><span data-stu-id="b2c4c-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="b2c4c-143">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b2c4c-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="b2c4c-144">每項調查都會針對 (*一* 項證據產生惡意、) 或沒有任何威脅。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="b2c4c-145">視威脅類型與結果不同，補救動作會自動發生，或經過貴組織安全性作業小組的核准。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="b2c4c-146">待處理和已完成的操作會列在[重要訊息中心](mtp-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="b2c4c-147">當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="b2c4c-148">如果在其他地方看到受感染的實體，則自動化調查將擴大其範圍，以包括該實體，並且將執行一般安全性劇本。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="b2c4c-149">並非每一個警示都會觸發自動化調查，而且並非每個調查都會觸發自動化修復動作;這完全取決於您組織的自動化調查與回應的安裝方式。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="b2c4c-150">請參閱 [Microsoft 365 Defender 中的設定](mtp-configure-auto-investigation-response.md)自動化調查與回應功能。</span><span class="sxs-lookup"><span data-stu-id="b2c4c-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="b2c4c-151">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b2c4c-151">Next steps</span></span>

- [<span data-ttu-id="b2c4c-152">瞭解 Microsoft 365 Defender 中自動化調查及回應的先決條件</span><span class="sxs-lookup"><span data-stu-id="b2c4c-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="b2c4c-153">為貴組織設定自動化調查與回應</span><span class="sxs-lookup"><span data-stu-id="b2c4c-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="b2c4c-154">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="b2c4c-154">Learn more about the Action center</span></span>](mtp-action-center.md)
