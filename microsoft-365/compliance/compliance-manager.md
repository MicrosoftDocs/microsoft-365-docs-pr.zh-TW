---
title: Microsoft 合規性管理員
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合規性管理員可協助組織簡化及自動化風險評估，並建議採取的措施以協助解決風險。
ms.openlocfilehash: d7136368a1c9726d1a77a0c99e717b98e1920242
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791801"
---
# <a name="microsoft-compliance-manager"></a><span data-ttu-id="09f0f-103">Microsoft 合規性管理員</span><span class="sxs-lookup"><span data-stu-id="09f0f-103">Microsoft Compliance Manager</span></span>

<span data-ttu-id="09f0f-104">**本文內容：** 瞭解合規性管理員是什麼，它如何協助簡化法規遵從性及降低風險，以及其重要元件。</span><span class="sxs-lookup"><span data-stu-id="09f0f-104">**In this article:** Learn what Compliance Manager is, how it helps simplify compliance and reduce risk, and its key components.</span></span>

## <a name="whats-new-the-ga-release-of-compliance-manager"></a><span data-ttu-id="09f0f-105">新功能：相容性管理員的公開發行版</span><span class="sxs-lookup"><span data-stu-id="09f0f-105">What's new: the GA release of Compliance Manager</span></span>

<span data-ttu-id="09f0f-106">合規性管理員現在已 (GA) 成為 [Microsoft 365 規範中心](microsoft-365-compliance-center.md)內的端對端規範管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="09f0f-106">Compliance Manager is now generally available (GA) as an end-to-end compliance management solution inside the [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span> <span data-ttu-id="09f0f-107">在此版本中，合規性管理員會從 Microsoft 服務信任入口網站中的先前位置轉換。</span><span class="sxs-lookup"><span data-stu-id="09f0f-107">With this release, Compliance Manager completes the transition from its previous location in the Microsoft Service Trust Portal.</span></span>

<span data-ttu-id="09f0f-108">公開的合規性分數的公開預覽已演變成集中式工具，其具有增強的合規性管理功能和更輕鬆使用。</span><span class="sxs-lookup"><span data-stu-id="09f0f-108">What began as the public preview of Compliance Score has evolved into a centralized tool with enhanced compliance management capabilities and greater ease of use.</span></span>  <span data-ttu-id="09f0f-109">GA 發行版本提供了更大的預先構建評估集合，可協助您擴大合規性活動。</span><span class="sxs-lookup"><span data-stu-id="09f0f-109">The GA release brings a larger collection of pre-built assessments to help you scale your compliance activities.</span></span>

<span data-ttu-id="09f0f-110">**深入瞭解 GA 版本：**</span><span class="sxs-lookup"><span data-stu-id="09f0f-110">**Learn more about the GA release:**</span></span>
- <span data-ttu-id="09f0f-111">我們的 [常見問題](compliance-manager-faq.md) 會逐步引導您深入瞭解演變。</span><span class="sxs-lookup"><span data-stu-id="09f0f-111">Our [frequently asked questions](compliance-manager-faq.md) walk you through the evolution in greater detail.</span></span>
- <span data-ttu-id="09f0f-112">閱讀 [此博客文章](https://aka.ms/compliancemanager/GAblog)中的 GA 功能增強功能。</span><span class="sxs-lookup"><span data-stu-id="09f0f-112">Read about GA feature enhancements in [this blog post](https://aka.ms/compliancemanager/GAblog).</span></span>

<span data-ttu-id="09f0f-113">觀看下列影片，瞭解合規性管理員如何協助簡化組織管理規範的方式：</span><span class="sxs-lookup"><span data-stu-id="09f0f-113">Watch the video below to learn how Compliance Manager can help simplify how your organization manages compliance:</span></span>
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a><span data-ttu-id="09f0f-114">何謂合規性管理員</span><span class="sxs-lookup"><span data-stu-id="09f0f-114">What is Compliance Manager</span></span>

<span data-ttu-id="09f0f-115">[Microsoft 合規性管理員](https://compliance.microsoft.com/compliancemanager) 是 [microsoft 365 規範中心](microsoft-365-compliance-center.md) 中的一項功能，可協助您管理組織的合規性需求，以提高便利性和便利性。</span><span class="sxs-lookup"><span data-stu-id="09f0f-115">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that helps you manage your organization’s compliance requirements with greater ease and convenience.</span></span> <span data-ttu-id="09f0f-116">合規性管理員可以協助您整個規範旅程，從清查您的資料保護風險到管理實施控制措施的複雜性、保持目前與法規和憑證的複雜性，以及向審計員報告。</span><span class="sxs-lookup"><span data-stu-id="09f0f-116">Compliance Manager can help you throughout your compliance journey, from taking inventory of your data protection risks to managing the complexities of implementing controls, staying current with regulations and certifications, and reporting to auditors.</span></span>

<span data-ttu-id="09f0f-117">合規性管理員提供下列功能，協助簡化法規遵從性並降低風險：</span><span class="sxs-lookup"><span data-stu-id="09f0f-117">Compliance Manager helps simplify compliance and reduce risk by providing:</span></span>

- <span data-ttu-id="09f0f-118">適用于一般行業和地區性標準及法規的預先建評估，或自訂評估以符合您的獨特法規遵從性需求 (可用評估取決於您的授權合約; [深入瞭解](https://go.microsoft.com/fwlink/?linkid=2132371)) 。</span><span class="sxs-lookup"><span data-stu-id="09f0f-118">Pre-built assessments for common industry and regional standards and regulations, or custom assessments to meet your unique compliance needs (available assessments depend on your licensing agreement; [learn more](https://go.microsoft.com/fwlink/?linkid=2132371)).</span></span>

- <span data-ttu-id="09f0f-119">工作流程功能，可協助您透過單一工具有效率地完成風險評估。</span><span class="sxs-lookup"><span data-stu-id="09f0f-119">Workflow capabilities to help you efficiently complete your risk assessments through a single tool.</span></span>

- <span data-ttu-id="09f0f-120">詳細的逐步指導方針，可協助您遵循組織最相關的標準及規定。</span><span class="sxs-lookup"><span data-stu-id="09f0f-120">Detailed step-by-step guidance on suggested improvement actions to help you comply with the standards and regulations that are most relevant for your organization.</span></span> <span data-ttu-id="09f0f-121">針對 Microsoft 所管理的動作，您將會看到「執行詳細資料」和「審計結果」。</span><span class="sxs-lookup"><span data-stu-id="09f0f-121">For actions that are managed by Microsoft, you’ll see implementation details and audit results.</span></span>

- <span data-ttu-id="09f0f-122">以風險為基礎的符合性分數，可協助您瞭解符合性狀況，方法是測量您完成改進動作的進度。</span><span class="sxs-lookup"><span data-stu-id="09f0f-122">A risk-based compliance score to help you understand your compliance posture by measuring your progress in completing improvement actions.</span></span>

<span data-ttu-id="09f0f-123">您的合規性管理員儀表板會顯示您目前的合規性分數，協助您瞭解需要注意的事項，並引導您進行重要改進動作。</span><span class="sxs-lookup"><span data-stu-id="09f0f-123">Your Compliance Manager dashboard shows your current compliance score, helps you see what needs attention, and guides you to key improvement actions.</span></span> <span data-ttu-id="09f0f-124">以下是合規性管理員儀表板外觀的範例：</span><span class="sxs-lookup"><span data-stu-id="09f0f-124">Below is an example of what your Compliance Manager dashboard will look like:</span></span>

<span data-ttu-id="09f0f-125">![合規性管理員-儀表板](../media/compliance-manager-dashboard.png "合規性管理員儀表板")</span><span class="sxs-lookup"><span data-stu-id="09f0f-125">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

## <a name="understanding-your-compliance-score"></a><span data-ttu-id="09f0f-126">瞭解您的合規性分數</span><span class="sxs-lookup"><span data-stu-id="09f0f-126">Understanding your compliance score</span></span>

<span data-ttu-id="09f0f-127">合規性管理員獎項您是為了完成遵循法規、標準或原則所採取的改進動作，並將這些點數結合為整體合規性分數。</span><span class="sxs-lookup"><span data-stu-id="09f0f-127">Compliance Manager awards you points for completing improvement actions taken to comply with a regulation, standard, or policy, and combines those points into an overall compliance score.</span></span> <span data-ttu-id="09f0f-128">每個動作對您的分數有不同的影響，取決於可能的風險。</span><span class="sxs-lookup"><span data-stu-id="09f0f-128">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="09f0f-129">您的合規性分數可協助您決定關注的動作，以改善您的整體相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="09f0f-129">Your compliance score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="09f0f-130">合規性管理員為您提供根據 Microsoft 365 資料保護基準的初始分數。</span><span class="sxs-lookup"><span data-stu-id="09f0f-130">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="09f0f-131">此基準是一組控制項，包含資料保護和一般資料控管的重要規章和標準。</span><span class="sxs-lookup"><span data-stu-id="09f0f-131">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="09f0f-132">深入了解</span><span class="sxs-lookup"><span data-stu-id="09f0f-132">Learn more</span></span>

<span data-ttu-id="09f0f-133">[瞭解如何計算您的合規性分數](compliance-score-calculation.md)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-133">[Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

<span data-ttu-id="09f0f-134">[瞭解如何使用 [改進] 動作](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-134">[Learn how to work with improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="09f0f-135">主要元素：控制項、評估、範本、改進動作</span><span class="sxs-lookup"><span data-stu-id="09f0f-135">Key elements: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="09f0f-136">合規性管理員使用多個資料元素，協助您管理相容性活動。</span><span class="sxs-lookup"><span data-stu-id="09f0f-136">Compliance Manager uses several data elements to help you manage your compliance activities.</span></span> <span data-ttu-id="09f0f-137">當您使用合規性管理員指派、測試及監視合規性活動時，讓基本瞭解主要元素非常有用： controls、評估、範本及改進動作。</span><span class="sxs-lookup"><span data-stu-id="09f0f-137">As you use Compliance Manager to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key elements: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="09f0f-138">控制項</span><span class="sxs-lookup"><span data-stu-id="09f0f-138">Controls</span></span>

<span data-ttu-id="09f0f-139">控制項是法規、標準或原則的必要條件。</span><span class="sxs-lookup"><span data-stu-id="09f0f-139">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="09f0f-140">它會定義如何評估和管理系統設定、組織處理常式，以及負責滿足法規、標準或原則的特定需求的人員。</span><span class="sxs-lookup"><span data-stu-id="09f0f-140">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="09f0f-141">合規性管理員會追蹤下列類型的控制項：</span><span class="sxs-lookup"><span data-stu-id="09f0f-141">Compliance Manager tracks the following types of controls:</span></span>

1. <span data-ttu-id="09f0f-142">**Microsoft managed controls** ： microsoft 雲端服務的控制項，microsoft 負責執行這種服務</span><span class="sxs-lookup"><span data-stu-id="09f0f-142">**Microsoft managed controls** : controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="09f0f-143">**您的控制項** ：有時候稱為客戶管理控制項，這些是由您的組織所實施及管理的控制項。</span><span class="sxs-lookup"><span data-stu-id="09f0f-143">**Your controls** : sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
3. <span data-ttu-id="09f0f-144">**共用控制項** ：這些是您的組織和 Microsoft 共同共同執行的控制措施</span><span class="sxs-lookup"><span data-stu-id="09f0f-144">**Shared controls** : these are controls that both your organization and Microsoft share responsibility for implementing</span></span>

##### <a name="learn-more"></a><span data-ttu-id="09f0f-145">深入了解</span><span class="sxs-lookup"><span data-stu-id="09f0f-145">Learn more</span></span>

<span data-ttu-id="09f0f-146">[監視控制項的進度](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-146">[Monitor progress of your controls](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).</span></span>

<span data-ttu-id="09f0f-147">[深入瞭解合規性管理員如何持續評估控制項](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-147">[Learn how Compliance Manager continuously assesses controls](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="09f0f-148">評估</span><span class="sxs-lookup"><span data-stu-id="09f0f-148">Assessments</span></span>

<span data-ttu-id="09f0f-149">評估是指來自特定法規、標準或原則的控制項群組。</span><span class="sxs-lookup"><span data-stu-id="09f0f-149">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="09f0f-150">完成評估內的動作可協助您符合標準、法規或法律的需求。</span><span class="sxs-lookup"><span data-stu-id="09f0f-150">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="09f0f-151">例如，您可能會有一個評估，當您完成其中的所有動作時，可協助您將 Microsoft 365 設定放入符合 ISO 27001 的需求。</span><span class="sxs-lookup"><span data-stu-id="09f0f-151">For example, you may have an assessment that, when you complete all actions within it, helps to bring your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="09f0f-152">評估包含數個元件：</span><span class="sxs-lookup"><span data-stu-id="09f0f-152">Assessments have several components:</span></span>

- <span data-ttu-id="09f0f-153">**範圍內的服務** ：適用于評估的特定 Microsoft 服務集合</span><span class="sxs-lookup"><span data-stu-id="09f0f-153">**In-scope services** : the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="09f0f-154">**Microsoft managed controls** ： microsoft 雲端服務的控制項，microsoft 代表您執行的動作</span><span class="sxs-lookup"><span data-stu-id="09f0f-154">**Microsoft managed controls** : controls for Microsoft cloud services, which Microsoft implements on your behalf</span></span>
- <span data-ttu-id="09f0f-155">**您的控制項** ：有時候稱為客戶管理控制項，這些是由您的組織所實施及管理的控制項。</span><span class="sxs-lookup"><span data-stu-id="09f0f-155">**Your controls** : sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
- <span data-ttu-id="09f0f-156">**共用控制項** ：這些是您的組織和 Microsoft 共同共同執行的控制措施</span><span class="sxs-lookup"><span data-stu-id="09f0f-156">**Shared controls** : these are controls that both your organization and Microsoft share responsibility for implementing</span></span>
- <span data-ttu-id="09f0f-157">**評估分數** ：顯示從評估中的動作到您的組織及 Microsoft 所管理的所有可能分數的進度</span><span class="sxs-lookup"><span data-stu-id="09f0f-157">**Assessment score** : shows your progress in achieving total possible points from actions within the assessment that are managed by your organization and by Microsoft</span></span>

<span data-ttu-id="09f0f-158">在建立評估時，您會將其指派給群組。</span><span class="sxs-lookup"><span data-stu-id="09f0f-158">When creating assessments, you’ll assign them to a group.</span></span> <span data-ttu-id="09f0f-159">您可以以組織最具邏輯的任何方式來設定群組。</span><span class="sxs-lookup"><span data-stu-id="09f0f-159">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="09f0f-160">例如，您可以透過審計年、地區、解決方案、組織內的小組或其他方式來群組評估。</span><span class="sxs-lookup"><span data-stu-id="09f0f-160">For example, you may group assessments by audit year, region, solution, teams within your organization, or some other way.</span></span> <span data-ttu-id="09f0f-161">一旦您建立群組，您就可以 [篩選合規性管理員儀表板](compliance-manager-setup.md#filtering-your-dashboard-view) ，以查看一或多個群組的分數。</span><span class="sxs-lookup"><span data-stu-id="09f0f-161">Once you create groups, you can [filter your Compliance Manager dashboard](compliance-manager-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="09f0f-162">深入了解</span><span class="sxs-lookup"><span data-stu-id="09f0f-162">Learn more</span></span>

<span data-ttu-id="09f0f-163">[在合規性管理員中建立及管理評估](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-163">[Build and manage assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="09f0f-164">範本</span><span class="sxs-lookup"><span data-stu-id="09f0f-164">Templates</span></span>

<span data-ttu-id="09f0f-165">合規性管理員提供範本，協助您快速建立評估。</span><span class="sxs-lookup"><span data-stu-id="09f0f-165">Compliance Manager provides templates to help you quickly create assessments.</span></span> <span data-ttu-id="09f0f-166">您可以修改這些範本，以依據您的需求建立評估優化。</span><span class="sxs-lookup"><span data-stu-id="09f0f-166">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="09f0f-167">您也可以建立具有您自己的控制項和動作的範本，以建立自訂評估。</span><span class="sxs-lookup"><span data-stu-id="09f0f-167">You can also build a custom assessment by creating a template with your own controls and actions.</span></span> <span data-ttu-id="09f0f-168">例如，您可能想要範本涵蓋內部的商務程式控制，或是一個 150 + 預先建立的評估範本未涵蓋的地區性資料保護標準。</span><span class="sxs-lookup"><span data-stu-id="09f0f-168">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our 150+ pre-built assessment templates.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="09f0f-169">深入了解</span><span class="sxs-lookup"><span data-stu-id="09f0f-169">Learn more</span></span>

<span data-ttu-id="09f0f-170">[查看合規性管理員所提供之評估範本的清單](compliance-manager-templates-list.md)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-170">[View the list of assessment templates provided by Compliance Manager](compliance-manager-templates-list.md).</span></span>

<span data-ttu-id="09f0f-171">[取得建立及修改評估範本的詳細指示](compliance-manager-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-171">[Get detailed instructions for creating and modifying templates for assessments](compliance-manager-templates.md).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="09f0f-172">改進動作</span><span class="sxs-lookup"><span data-stu-id="09f0f-172">Improvement actions</span></span>

<span data-ttu-id="09f0f-173">改進的動作有助於集中執行您的合規性活動。</span><span class="sxs-lookup"><span data-stu-id="09f0f-173">Improvement actions help centralize your compliance activities.</span></span> <span data-ttu-id="09f0f-174">每個改進動作都提供建議的指導方針，以協助您與資料保護法規和標準相符。</span><span class="sxs-lookup"><span data-stu-id="09f0f-174">Each improvement action provides recommended guidance that’s intended to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="09f0f-175">您可以將改進動作指派給組織中的使用者，以執行實施和測試工作。</span><span class="sxs-lookup"><span data-stu-id="09f0f-175">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="09f0f-176">您也可以在改進動作中儲存檔、記事及記錄狀態更新。</span><span class="sxs-lookup"><span data-stu-id="09f0f-176">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="09f0f-177">深入了解</span><span class="sxs-lookup"><span data-stu-id="09f0f-177">Learn more</span></span>

<span data-ttu-id="09f0f-178">[使用提高的動作來管理您的合規性工作流程](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-178">[Use improvement actions to manage your compliance workflow](compliance-manager-improvement-actions.md).</span></span>

<span data-ttu-id="09f0f-179">[深入瞭解動作會如何影響您的合規性分數](compliance-score-calculation.md#action-types-and-points)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-179">[Learn how actions impact your compliance score](compliance-score-calculation.md#action-types-and-points).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="09f0f-180">支援的語言</span><span class="sxs-lookup"><span data-stu-id="09f0f-180">Supported languages</span></span>

<span data-ttu-id="09f0f-181">合規性管理員可以採用下列語言：</span><span class="sxs-lookup"><span data-stu-id="09f0f-181">Compliance Manager is available in the following languages:</span></span>

- <span data-ttu-id="09f0f-182">英文</span><span class="sxs-lookup"><span data-stu-id="09f0f-182">English</span></span>
- <span data-ttu-id="09f0f-183">Bahasa 印尼</span><span class="sxs-lookup"><span data-stu-id="09f0f-183">Bahasa Indonesian</span></span>
- <span data-ttu-id="09f0f-184">Bahasa 馬來</span><span class="sxs-lookup"><span data-stu-id="09f0f-184">Bahasa Malay</span></span>
- <span data-ttu-id="09f0f-185">簡體中文</span><span class="sxs-lookup"><span data-stu-id="09f0f-185">Chinese (Simplified)</span></span>
- <span data-ttu-id="09f0f-186">繁體中文</span><span class="sxs-lookup"><span data-stu-id="09f0f-186">Chinese (Traditional)</span></span>
- <span data-ttu-id="09f0f-187">捷克文</span><span class="sxs-lookup"><span data-stu-id="09f0f-187">Czech</span></span>
- <span data-ttu-id="09f0f-188">丹麥文</span><span class="sxs-lookup"><span data-stu-id="09f0f-188">Danish</span></span>
- <span data-ttu-id="09f0f-189">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="09f0f-189">Dutch</span></span>
- <span data-ttu-id="09f0f-190">芬蘭文</span><span class="sxs-lookup"><span data-stu-id="09f0f-190">Finnish</span></span>
- <span data-ttu-id="09f0f-191">法文</span><span class="sxs-lookup"><span data-stu-id="09f0f-191">French</span></span>
- <span data-ttu-id="09f0f-192">德文</span><span class="sxs-lookup"><span data-stu-id="09f0f-192">German</span></span>
- <span data-ttu-id="09f0f-193">希伯來文</span><span class="sxs-lookup"><span data-stu-id="09f0f-193">Hebrew</span></span>
- <span data-ttu-id="09f0f-194">匈牙利文</span><span class="sxs-lookup"><span data-stu-id="09f0f-194">Hungarian</span></span>
- <span data-ttu-id="09f0f-195">義大利文</span><span class="sxs-lookup"><span data-stu-id="09f0f-195">Italian</span></span>
- <span data-ttu-id="09f0f-196">日文</span><span class="sxs-lookup"><span data-stu-id="09f0f-196">Japanese</span></span>
- <span data-ttu-id="09f0f-197">韓文</span><span class="sxs-lookup"><span data-stu-id="09f0f-197">Korean</span></span>
- <span data-ttu-id="09f0f-198">挪威文</span><span class="sxs-lookup"><span data-stu-id="09f0f-198">Norwegian</span></span>
- <span data-ttu-id="09f0f-199">波蘭文</span><span class="sxs-lookup"><span data-stu-id="09f0f-199">Polish</span></span>
- <span data-ttu-id="09f0f-200">葡萄牙文 (巴西) </span><span class="sxs-lookup"><span data-stu-id="09f0f-200">Portuguese (Brazilian)</span></span>
- <span data-ttu-id="09f0f-201">俄文</span><span class="sxs-lookup"><span data-stu-id="09f0f-201">Russian</span></span>
- <span data-ttu-id="09f0f-202">西班牙文</span><span class="sxs-lookup"><span data-stu-id="09f0f-202">Spanish</span></span>
- <span data-ttu-id="09f0f-203">瑞典文</span><span class="sxs-lookup"><span data-stu-id="09f0f-203">Swedish</span></span>
- <span data-ttu-id="09f0f-204">泰文</span><span class="sxs-lookup"><span data-stu-id="09f0f-204">Thai</span></span>
- <span data-ttu-id="09f0f-205">土耳其文</span><span class="sxs-lookup"><span data-stu-id="09f0f-205">Turkish</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="09f0f-206">後續步驟：設定和自訂</span><span class="sxs-lookup"><span data-stu-id="09f0f-206">Next steps: set up and customize</span></span>

<span data-ttu-id="09f0f-207">瞭解如何登入、指派許可權和角色、設定設定，以及在 [開始使用合規性管理員](compliance-manager-setup.md)時個人化儀表板視圖。</span><span class="sxs-lookup"><span data-stu-id="09f0f-207">Learn how to sign in, assign permissions and roles, configure settings, and personalize your dashboard view at [Get started with Compliance Manager](compliance-manager-setup.md).</span></span>

<span data-ttu-id="09f0f-208">然後開始自訂合規性管理員，以協助您遵循對組織最重要的行業標準， [設定評估](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="09f0f-208">Then start customizing Compliance Manager to help you comply with industry standards that matter most to your organization by [setting up assessments](compliance-manager-assessments.md).</span></span>