---
title: Microsoft 合規性分數（預覽）
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合規性分數（預覽）可協助組織簡化及自動化風險評估，並建議採取的措施以協助解決風險。
ms.openlocfilehash: 0cb8bd0b5aa39be2a9a6e706afa21bb7dc53eadb
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016136"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="c4a6f-103">Microsoft 合規性分數（預覽）</span><span class="sxs-lookup"><span data-stu-id="c4a6f-103">Microsoft Compliance Score (preview)</span></span>

<span data-ttu-id="c4a6f-104">**本文內容：** 瞭解遵循的合規性分數、它如何協助簡化管理規範的方式，以及如何為您的組織加以設定。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-104">**In this article:** Learn what Compliance Score is, how it helps simplify the way you manage compliance, and how to set it up for your organization.</span></span>

<span data-ttu-id="c4a6f-105">**新功能：** 2020年6月的版本包含建立及管理評估的新功能，以及在合規性分數中查看控制項的功能。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-105">**What's new:** The June 2020 release includes new functionality to create and manage assessments, and to view controls within Compliance Score.</span></span> <span data-ttu-id="c4a6f-106">請造訪「[合規性分數版本](compliance-score-release-notes.md)資訊」，以查看相容性分數公開預覽中的新功能。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-106">Visit the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new in the public preview of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="c4a6f-107">合規性分數為何</span><span class="sxs-lookup"><span data-stu-id="c4a6f-107">What is Compliance Score</span></span>

<span data-ttu-id="c4a6f-108">[Microsoft 合規性分數](https://compliance.microsoft.com/compliancescore)是[microsoft 365 規範中心](microsoft-365-compliance-center.md)的預覽功能，可協助您瞭解組織的合規性狀況。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-108">[Microsoft Compliance Score](https://compliance.microsoft.com/compliancescore) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture.</span></span> <span data-ttu-id="c4a6f-109">它會計算以風險為基礎的分數，用以衡量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-109">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="c4a6f-110">您可以使用合規性分數做為工具，以追蹤所有風險評估。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-110">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="c4a6f-111">它提供工作流程功能，協助您透過一般工具，有效地完成風險評估。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-111">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="c4a6f-112">[合規性管理員](compliance-manager-overview.md)使用者會注意到「合規性分數」現在是獨立的功能，具有更簡單、更便於使用的設計，可協助組織更輕鬆地管理規範。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-112">[Compliance Manager](compliance-manager-overview.md) users will notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help organizations more easily manage compliance.</span></span>

<span data-ttu-id="c4a6f-113">主要合規性分數頁面是您的自訂儀表板。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-113">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="c4a6f-114">它會顯示您目前的評分，協助您瞭解需要注意的事項，並指導您採取動作以提升您的分數。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-114">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="c4a6f-115">您的合規性分數儀表板看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="c4a6f-115">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="c4a6f-116">![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="c4a6f-116">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="c4a6f-117">簡化的規範管理</span><span class="sxs-lookup"><span data-stu-id="c4a6f-117">Simplified compliance management</span></span>

<span data-ttu-id="c4a6f-118">合規性分數可提供下列功能，以簡化規範管理：</span><span class="sxs-lookup"><span data-stu-id="c4a6f-118">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="c4a6f-119">**連續評估**：自動掃描您的 Microsoft 365 環境，以偵測和監視系統中資料保護控制項的效能</span><span class="sxs-lookup"><span data-stu-id="c4a6f-119">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="c4a6f-120">**建議的動作**：提供建議，並逐步指導您如何執行控制以最大化排名</span><span class="sxs-lookup"><span data-stu-id="c4a6f-120">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="c4a6f-121">**內建的控制項對應**：透過提供內建的共同作業架構，協助您在不斷提高的規範環境中保持最新狀態</span><span class="sxs-lookup"><span data-stu-id="c4a6f-121">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4a6f-122">您不應將「合規性分數」和「合規性管理員」中的建議視為合規性的保證。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-122">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="c4a6f-123">您可以根據法規環境評估和驗證客戶控制措施的效能。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-123">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="c4a6f-124">這些服務目前是在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-124">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="c4a6f-125">另請參閱[Microsoft 365 授權指南以取得安全性和合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-125">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="c4a6f-126">與合規性管理員的關係</span><span class="sxs-lookup"><span data-stu-id="c4a6f-126">Relationship to Compliance Manager</span></span>

<span data-ttu-id="c4a6f-127">請將合規性分數視為合規性管理員簡化的體驗。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-127">Think of Compliance Score as a simplified experience of Compliance Manager.</span></span> <span data-ttu-id="c4a6f-128">雖然這兩者都存在於不同的整合式工具中，但遵從性分數可讓您更容易監視整體的相容性狀況，並採取步驟加以改善。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-128">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="c4a6f-129">合規性分數與合規性管理員分享相同的後端。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-129">Compliance Score shares the same backend with Compliance Manager.</span></span> <span data-ttu-id="c4a6f-130">您在某項工具中執行的任何動作都會以其他工具呈現。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-130">Anything that you do in one tool will surface in the other tool.</span></span>

<span data-ttu-id="c4a6f-131">在公開預覽期間，評估與範本管理的某些功能仍會保留在合規性管理員中。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-131">Some functionality for assessment and template management remains in Compliance Manager during public preview.</span></span> <span data-ttu-id="c4a6f-132">建議您在合規性分數中開始所有符合性管理活動。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-132">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="c4a6f-133">當您接觸合規性管理員所處理的功能時，我們會在這裡為您提供指導。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-133">When you come to functions handled by Compliance Manager, we’ll guide you there.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="c4a6f-134">深入了解</span><span class="sxs-lookup"><span data-stu-id="c4a6f-134">Learn more</span></span>

<span data-ttu-id="c4a6f-135">[瞭解合規性分數和合規性管理員之間的關係](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-135">[Understand the relationship between Compliance Score and Compliance Manager](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="c4a6f-136">瞭解您的分數</span><span class="sxs-lookup"><span data-stu-id="c4a6f-136">Understanding your score</span></span>

<span data-ttu-id="c4a6f-137">合規性分數獎項您可以針對遵守法規、標準或原則所採取的措施進行積分。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-137">Compliance Score awards you points for completing actions taken to comply with a regulation, standard, or policy.</span></span> <span data-ttu-id="c4a6f-138">每個動作對您的分數有不同的影響，取決於可能的風險。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-138">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="c4a6f-139">您的分數可協助您決定關注的動作，以改善您的整體相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-139">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="c4a6f-140">合規性分數為您提供以 Microsoft 365 資料保護基準為基礎的初始分數。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-140">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span>  <span data-ttu-id="c4a6f-141">此基準是一組控制項，包含資料保護和一般資料控管的重要規章和標準。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-141">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="c4a6f-142">此基準主要是從 NIST CSF （國家標準和技術協會 Cybersecurity Framework）和 ISO （國際標準組織的標準化 FedRAMP）和 GDPR （歐盟的一般資料保護法規）和（一般資料保護法規）中的專案來繪製要素。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-142">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="c4a6f-143">資料保護基準評估是用來計算您的初始分數，然後再設定其他評估。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-143">The data protection baseline assessment is used to calculate your initial score before you configure any other assessments.</span></span> <span data-ttu-id="c4a6f-144">在您第一次造訪時，合規性分數已經從您的 Microsoft 365 解決方案中收集信號。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-144">Upon your first visit, Compliance Score is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="c4a6f-145">您將會很快看到組織相對於重要資料保護標準與法規的執行方式，並查看建議採取的改進動作。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-145">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="c4a6f-146">由於每個組織都有特定需求，因此符合您的需求取決於您設定和管理您自己的評估，以更好地緩解風險。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-146">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to better mitigate risks.</span></span> <span data-ttu-id="c4a6f-147">例如，如果您的組織屬於金融服務行業，您可能會想要新增 FFIEC 評估。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-147">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="c4a6f-148">如果您的組織屬於醫療保健行業，您可以新增 HIPAA/高科技評估。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-148">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="c4a6f-149">深入了解</span><span class="sxs-lookup"><span data-stu-id="c4a6f-149">Learn more</span></span>

<span data-ttu-id="c4a6f-150">[瞭解如何計算和持續監控規範分數](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-150">[Understand how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>

<span data-ttu-id="c4a6f-151">[在合規性分數中建立及管理評估](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-151">[Create and manage assessments in Compliance Score](compliance-score-assessments.md).</span></span>

## <a name="key-components-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="c4a6f-152">主要元件：控制項、評估、範本、改進動作</span><span class="sxs-lookup"><span data-stu-id="c4a6f-152">Key components: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="c4a6f-153">合規性分數使用多個元件，協助您管理相容性活動。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-153">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="c4a6f-154">當您使用相容性分數指派、測試及監視合規性活動時，對重要元件具有基本的瞭解會很有説明：控制項、評估、範本及改進動作。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-154">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key components: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="c4a6f-155">控制項</span><span class="sxs-lookup"><span data-stu-id="c4a6f-155">Controls</span></span>

<span data-ttu-id="c4a6f-156">控制項是法規、標準或原則的必要條件。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-156">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="c4a6f-157">它會定義如何評估和管理系統設定、組織處理常式，以及負責滿足法規、標準或原則的特定需求的人員。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-157">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="c4a6f-158">合規性分數追蹤兩種類型的控制項：</span><span class="sxs-lookup"><span data-stu-id="c4a6f-158">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="c4a6f-159">**Microsoft managed controls**： microsoft 雲端服務的控制項，microsoft 負責執行這種服務</span><span class="sxs-lookup"><span data-stu-id="c4a6f-159">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="c4a6f-160">**您的控制項**：有時候稱為客戶控制項，這些是由您的組織所實施及管理的控制項。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-160">**Your controls**: sometimes referred to as customer controls, these are controls implemented and managed by your organization</span></span>

#### <a name="learn-more"></a><span data-ttu-id="c4a6f-161">深入了解</span><span class="sxs-lookup"><span data-stu-id="c4a6f-161">Learn more</span></span>

<span data-ttu-id="c4a6f-162">[監視控制項的進度](compliance-score-assessments.md#monitor-assessment-progress-and-controls)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-162">[Monitor progress of your controls](compliance-score-assessments.md#monitor-assessment-progress-and-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="c4a6f-163">評估</span><span class="sxs-lookup"><span data-stu-id="c4a6f-163">Assessments</span></span>

<span data-ttu-id="c4a6f-164">評估是指來自特定法規、標準或原則的控制項群組。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-164">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="c4a6f-165">完成評估內的動作可協助您符合標準、法規或法律的需求。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-165">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="c4a6f-166">例如，您可能會有一個評估，當您完成其中的所有動作時，會以 ISO 27001 需求為依據，使您的 Microsoft 365 設定成為線上。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-166">For example, you may have an assessment that, when you complete all actions within it, brings your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="c4a6f-167">評估包含數個元件：</span><span class="sxs-lookup"><span data-stu-id="c4a6f-167">Assessments have several components:</span></span>

- <span data-ttu-id="c4a6f-168">**範圍內的服務**：適用于評估的特定 Microsoft 服務集合</span><span class="sxs-lookup"><span data-stu-id="c4a6f-168">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="c4a6f-169">**Microsoft managed controls**： microsoft 實施及測試的控制項</span><span class="sxs-lookup"><span data-stu-id="c4a6f-169">**Microsoft managed controls**: controls that Microsoft implements and tests</span></span>
- <span data-ttu-id="c4a6f-170">**您的控制項**：您管理的控制項</span><span class="sxs-lookup"><span data-stu-id="c4a6f-170">**Your controls**: controls that you manage</span></span>
- <span data-ttu-id="c4a6f-171">**評估分數**：完成該評估中的改進動作所能達到的點數百分比</span><span class="sxs-lookup"><span data-stu-id="c4a6f-171">**Assessment score**: the percentage of the points achieved by completing improvement actions within that assessment</span></span>

<span data-ttu-id="c4a6f-172">在建立評估時，您會將其指派給**群組**。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-172">When creating assessments, you'll assign them to a **group**.</span></span> <span data-ttu-id="c4a6f-173">您可以以組織最具邏輯的任何方式來設定群組。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-173">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="c4a6f-174">例如，您可以依年、組織內的符合性標準、服務、小組或其他方式來群組評估。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-174">For example, you may group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span> <span data-ttu-id="c4a6f-175">一旦您建立群組，您就可以[篩選「合規性分數」儀表板](compliance-score-setup.md#filtering-your-dashboard-view)，以查看一或多個群組的分數。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-175">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="c4a6f-176">深入了解</span><span class="sxs-lookup"><span data-stu-id="c4a6f-176">Learn more</span></span>

<span data-ttu-id="c4a6f-177">[在合規性分數中建立及管理評估](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-177">[Create and manage assessments in Compliance Score](compliance-score-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="c4a6f-178">範本</span><span class="sxs-lookup"><span data-stu-id="c4a6f-178">Templates</span></span>

<span data-ttu-id="c4a6f-179">合規性分數提供可讓您快速建立評估的範本。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-179">Compliance Score provides templates that are ready for you to quickly create assessments.</span></span> <span data-ttu-id="c4a6f-180">您可以修改這些範本，以依據您的需求建立評估優化。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-180">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="c4a6f-181">您也可以使用自己的控制項和動作來開發您自己的範本，以建立自訂評估。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-181">You can also create a Custom Assessment by developing your own template with your own controls and actions.</span></span> <span data-ttu-id="c4a6f-182">例如，您可能想要範本涵蓋內部的商務程式控制，或一個我們的範本未涵蓋的地區性資料保護標準。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-182">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our templates.</span></span>

<span data-ttu-id="c4a6f-183">建立您自己的範本，讓您不僅可以追蹤 Microsoft 雲端評估，還可以追蹤組織範圍內的任何其他風險評估。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-183">Creating your own templates lets you track not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="c4a6f-184">深入了解</span><span class="sxs-lookup"><span data-stu-id="c4a6f-184">Learn more</span></span>

<span data-ttu-id="c4a6f-185">[在建立評估時，查看合規性分數中可用的範本](compliance-score-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-185">[View the templates available in Compliance Score for building assessments](compliance-score-templates.md).</span></span>

<span data-ttu-id="c4a6f-186">[取得建立及修改範本合規性管理員的詳細指示](working-with-compliance-manager.md#templates)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-186">[Get detailed instructions for creating and modifying templates Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="c4a6f-187">改進動作</span><span class="sxs-lookup"><span data-stu-id="c4a6f-187">Improvement actions</span></span>

<span data-ttu-id="c4a6f-188">改進相容性活動的改進動作。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-188">Improvement actions centralize your compliance activities.</span></span> <span data-ttu-id="c4a6f-189">每個改進動作都提供詳細的執行指導，以協助您與資料保護法規和標準相符。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-189">Each improvement action gives detailed implementation guidance to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="c4a6f-190">動作可指派給組織中的使用者，以執行實施和測試工作。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-190">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="c4a6f-191">您也可以在改進動作中儲存檔、記事及記錄狀態更新。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-191">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="c4a6f-192">深入了解</span><span class="sxs-lookup"><span data-stu-id="c4a6f-192">Learn more</span></span>

<span data-ttu-id="c4a6f-193">[使用提高的動作來管理您的合規性工作流程](compliance-score-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-193">[Use improvement actions to manage your compliance workflow](compliance-score-improvement-actions.md).</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="c4a6f-194">後續步驟：設定和自訂</span><span class="sxs-lookup"><span data-stu-id="c4a6f-194">Next steps: set up and customize</span></span>

<span data-ttu-id="c4a6f-195">瞭解如何登入、設定許可權和角色、設定安全分數更新，以及在[相容性分數設定](compliance-score-setup.md)時個人化儀表板視圖。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-195">Learn how to sign in, set permissions and roles, configure Secure Score updates, and personalize your dashboard view at [Compliance Score setup](compliance-score-setup.md).</span></span>

<span data-ttu-id="c4a6f-196">然後，[設定評估](compliance-score-assessments.md)以開始自訂群組織的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="c4a6f-196">Then start customizing Compliance Score for your organization by [setting up assessments](compliance-score-assessments.md).</span></span>