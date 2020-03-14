---
title: Microsoft 合規性分數
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
description: Microsoft 合規性分數可協助組織簡化及自動化風險評估，並建議採取建議的動作以協助解決風險。
ms.openlocfilehash: dff5e6c057df37c076e328d5203a1eb4e4b3207a
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635111"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="9d7b8-103">Microsoft 合規性分數（預覽）</span><span class="sxs-lookup"><span data-stu-id="9d7b8-103">Microsoft Compliance Score (Preview)</span></span>

<span data-ttu-id="9d7b8-104">Microsoft 合規性分數可協助您簡化管理法規遵從性的方式，並透過方便使用的經驗降低法規遵從性風險。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-104">Microsoft Compliance Score helps to simplify the way you manage compliance and reduce compliance risks through a user-friendly experience.</span></span> <span data-ttu-id="9d7b8-105">合規性分數現在適用于[Microsoft 365 規範中心](microsoft-365-compliance-center.md)內的公開預覽。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-105">Compliance Score is now available for public preview in the  [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>

<span data-ttu-id="9d7b8-106">**本文內容：** 請閱讀本文，以瞭解哪些相容性分數，以及如何為您的組織設定。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-106">**In this article:** Read this article to understand what Compliance Score is and how to set it up for your organization.</span></span>

<span data-ttu-id="9d7b8-107">**深入瞭解更新：** 請移至「[合規性分數版本](compliance-score-release-notes.md)資訊」，以查看「預覽」版本的合規性分數的新功能和已知問題。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-107">**Learn about updates:** Go to the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new and known issues with the preview version of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="9d7b8-108">合規性分數為何</span><span class="sxs-lookup"><span data-stu-id="9d7b8-108">What is Compliance Score</span></span>

<span data-ttu-id="9d7b8-109">Microsoft 合規性分數是 Microsoft 365 規範中心的預覽功能，可協助您瞭解組織的合規性狀況。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-109">Microsoft Compliance Score is a preview feature in the Microsoft 365 compliance center to help you understand your organization’s compliance posture.</span></span> <span data-ttu-id="9d7b8-110">它會計算以風險為基礎的分數，用以衡量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-110">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="9d7b8-111">您可以使用合規性分數做為工具，以追蹤所有風險評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-111">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="9d7b8-112">它提供工作流程功能，協助您透過一般工具，有效地完成風險評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-112">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="9d7b8-113">如果您目前使用[合規性管理員](compliance-manager-overview.md)，您會注意到「合規性分數」現在是獨立的功能，具有更簡單且便於使用的設計，可協助您更輕鬆地管理規範。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-113">If you currently use [Compliance Manager](compliance-manager-overview.md), you’ll notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help you manage compliance more easily.</span></span> 

<span data-ttu-id="9d7b8-114">主要合規性分數頁面是您的自訂儀表板。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-114">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="9d7b8-115">它會顯示您目前的評分，協助您瞭解需要注意的事項，並指導您採取動作以提升您的分數。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-115">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="9d7b8-116">您的合規性分數儀表板看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="9d7b8-116">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="9d7b8-117">![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="9d7b8-117">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="9d7b8-118">簡化的規範管理</span><span class="sxs-lookup"><span data-stu-id="9d7b8-118">Simplified compliance management</span></span>

<span data-ttu-id="9d7b8-119">合規性分數可提供下列功能，以簡化規範管理：</span><span class="sxs-lookup"><span data-stu-id="9d7b8-119">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="9d7b8-120">**連續評估**：自動掃描您的 Microsoft 365 環境，以偵測和監視系統中資料保護控制項的效能</span><span class="sxs-lookup"><span data-stu-id="9d7b8-120">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="9d7b8-121">**建議的動作**：提供建議，並逐步指導您如何執行控制以最大化排名</span><span class="sxs-lookup"><span data-stu-id="9d7b8-121">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="9d7b8-122">**內建的控制項對應**：透過提供內建的共同作業架構，協助您在不斷提高的規範環境中保持最新狀態</span><span class="sxs-lookup"><span data-stu-id="9d7b8-122">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="9d7b8-123">合規性分數不會明確組織符合任何特定標準或法規的絕對度量。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-123">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="9d7b8-124">它表示您已採用控制的程度，可降低個人資料和個別隱私權的風險。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-124">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="9d7b8-125">符合性分數和合規性管理員的建議不得加以轉譯以保證法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-125">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="9d7b8-126">這項服務目前在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-126">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="9d7b8-127">與合規性管理員的關係</span><span class="sxs-lookup"><span data-stu-id="9d7b8-127">Relationship to Compliance Manager</span></span>

<span data-ttu-id="9d7b8-128">請將合規性分數視為合規性管理員簡化版本。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-128">Think of Compliance Score as a simplified version of Compliance Manager.</span></span> <span data-ttu-id="9d7b8-129">雖然這兩者都存在於不同的整合式工具中，但遵從性分數可讓您更容易監視整體的相容性狀況，並採取步驟加以改善。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-129">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="9d7b8-130">合規性分數與合規性管理員共用相同的後端，所以合規性管理員中您可能已具備的任何資料都會以相容性分數顯示。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-130">Compliance Score shares the same backend with Compliance Manager, so any data you may already have in Compliance Manager will show in Compliance Score.</span></span>

<span data-ttu-id="9d7b8-131">在公開預覽期間，有些功能會維持在合規性管理員內，例如管理評估和建立範本。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-131">During public preview, some functionality remains solely in Compliance Manager, such as managing assessments and creating templates.</span></span> <span data-ttu-id="9d7b8-132">建議您在合規性分數中開始所有符合性管理活動。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-132">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="9d7b8-133">當您前往合規性管理員所處理的功能時，系統會引導您進入該工具。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-133">When you come to functions handled by Compliance Manager, you will be guided to that tool.</span></span> <span data-ttu-id="9d7b8-134">基於此原因，本文中的一些檔會將您導向合規性管理員主題。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-134">For that reason, some of this documentation directs you to Compliance Manager topics.</span></span>

<span data-ttu-id="9d7b8-135">深入瞭解[合規性分數版本附注](compliance-score-release-notes.md)中的合規性分數和合規性管理員之間的關係。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-135">Learn more about the relationship between Compliance Score and Compliance Manager in the [Compliance Score release notes](compliance-score-release-notes.md).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="9d7b8-136">瞭解您的分數</span><span class="sxs-lookup"><span data-stu-id="9d7b8-136">Understanding your score</span></span>

<span data-ttu-id="9d7b8-137">合規性分數為您提供以 Microsoft 365 資料保護基準為基礎的初始分數。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-137">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="9d7b8-138">此基準是一組包含常見工業法規和標準的控制項。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-138">This baseline is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="9d7b8-139">雖然這個分數是評估符合性狀況的好開端，但一旦您新增了與貴組織更為相關的評估，就會變得更強大。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-139">While this score is a good starting point for assessing your compliance posture, Compliance Score becomes more powerful once you add assessments that are more relevant to your organization.</span></span>

<span data-ttu-id="9d7b8-140">例如，如果您的組織屬於金融服務行業，您可能會想要新增 FFIEC 評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-140">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="9d7b8-141">如果您的組織屬於醫療保健行業，您可以新增 HIPAA/高科技評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-141">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span> <span data-ttu-id="9d7b8-142">瞭解如何[在合規性管理員中新增評估](working-with-compliance-manager.md#assessments)。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-142">Learn how to [add assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

<span data-ttu-id="9d7b8-143">深入瞭解[如何計算和持續監控規範分數](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-143">Learn more about [how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>


## <a name="key-components-controls-assessments-templates-groups"></a><span data-ttu-id="9d7b8-144">主要元件：控制項、評估、範本、群組</span><span class="sxs-lookup"><span data-stu-id="9d7b8-144">Key components: controls, assessments, templates, groups</span></span>

<span data-ttu-id="9d7b8-145">合規性分數使用多個元件，協助您管理相容性活動。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-145">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="9d7b8-146">當您使用相容性分數指派、測試及監視合規性活動時，對這些重要元件有基本瞭解會很有説明。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-146">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of these key components.</span></span> <span data-ttu-id="9d7b8-147">此圖顯示兩者之間的關係：</span><span class="sxs-lookup"><span data-stu-id="9d7b8-147">This diagram shows the relationships among them:</span></span>

<span data-ttu-id="9d7b8-148">![合規性管理員第3版中的關係](../media/compliance-manager-relationships.png "合規性分陣列件")</span><span class="sxs-lookup"><span data-stu-id="9d7b8-148">![Relationships in Compliance Manager Version 3](../media/compliance-manager-relationships.png "Compliance Score components")</span></span>

### <a name="controls"></a><span data-ttu-id="9d7b8-149">控制項</span><span class="sxs-lookup"><span data-stu-id="9d7b8-149">Controls</span></span>

<span data-ttu-id="9d7b8-150">控制項定義如何評估和管理系統設定、組織程式和人員責任，以符合法規、標準或內部原則的特定需求。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-150">A control defines how you assess and manage system configuration, organizational process, and people accountability to meet a specific requirement of a regulation, standard, or internal policy.</span></span>

<span data-ttu-id="9d7b8-151">合規性分數追蹤兩種類型的控制項：</span><span class="sxs-lookup"><span data-stu-id="9d7b8-151">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="9d7b8-152">**Microsoft 受管理的控制項**： microsoft cloud services 的控制項，microsoft 負責執行這種服務</span><span class="sxs-lookup"><span data-stu-id="9d7b8-152">**Microsoft-managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="9d7b8-153">**客戶管理的控制項**：由您的組織管理的控制項，您負責執行這些控制項。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-153">**Customer-managed controls**: controls managed by your organization, which you are responsible for implementing</span></span>
 
### <a name="assessments"></a><span data-ttu-id="9d7b8-154">評估</span><span class="sxs-lookup"><span data-stu-id="9d7b8-154">Assessments</span></span>

<span data-ttu-id="9d7b8-155">評估是一項範本評估，可對您的組織發起計分程式。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-155">An assessment is an evaluation of a template that initiates the scoring process for your organization.</span></span> <span data-ttu-id="9d7b8-156">評估群組符合標準、法規或法律需求所需的動作。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-156">Assessments group the actions necessary to meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="9d7b8-157">例如，您可能會有一個評估，當您完成其中的所有動作時，您的 Office 365 設定會以 ISO 27001 的需求為依據。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-157">For example, you may have an assessment that, when you complete all actions within it, brings your Office 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="9d7b8-158">根據預設，相容性分數會為您的組織提供以 Microsoft 365 資料保護基準進行評估的建議，以降低資料保護和合規性風險的建議（[深入瞭解](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-158">By default, Compliance Score provides your organization with an assessment based on the Microsoft 365 data protection baseline, a recommendation for reducing your data protection and compliance risks ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

<span data-ttu-id="9d7b8-159">評估包含數個元件：</span><span class="sxs-lookup"><span data-stu-id="9d7b8-159">Assessments include several components:</span></span>

- <span data-ttu-id="9d7b8-160">**範圍內的服務**：適用于評估的特定 Microsoft 服務集合</span><span class="sxs-lookup"><span data-stu-id="9d7b8-160">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="9d7b8-161">**Microsoft 管理控制項**： microsoft 所實施及測試的控制項</span><span class="sxs-lookup"><span data-stu-id="9d7b8-161">**Microsoft-managed controls**: controls that Microsoft implemented and tested</span></span>
- <span data-ttu-id="9d7b8-162">**客戶管理的控制項**：您管理的控制項</span><span class="sxs-lookup"><span data-stu-id="9d7b8-162">**Customer-managed controls**: controls that you manage</span></span>
- <span data-ttu-id="9d7b8-163">**評估分數**：完成該評估中的動作可取得的點數百分比</span><span class="sxs-lookup"><span data-stu-id="9d7b8-163">**Assessment score**: the percentage of the points achieved by completing actions within that assessment</span></span>

> [!NOTE]
> <span data-ttu-id="9d7b8-164">合規性分數會顯示您的評估，以及它們如何影響您的整體分數。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-164">Compliance Score displays your assessments and how they factor into your overall score.</span></span> <span data-ttu-id="9d7b8-165">不過，在公開預覽期間，系統會將您導向合規性管理員以管理評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-165">However, during public preview you will be directed to Compliance Manager to manage your assessments.</span></span>

<span data-ttu-id="9d7b8-166">[在合規性管理員中](working-with-compliance-manager.md#assessments)查看使用評估的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-166">View detailed instructions for [working with assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

### <a name="templates"></a><span data-ttu-id="9d7b8-167">範本</span><span class="sxs-lookup"><span data-stu-id="9d7b8-167">Templates</span></span>

<span data-ttu-id="9d7b8-168">合規性分數可提供預先設定的範本進行評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-168">Compliance Score provides pre-configured templates for assessments.</span></span> <span data-ttu-id="9d7b8-169">合規性分數也可讓您建立自己評估的範本，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-169">Compliance Score also allows you to create templates for your own assessments to suit your needs.</span></span> <span data-ttu-id="9d7b8-170">例如，您可以為商務程式控制建立範本，或為區域資料保護或符合性標準（其中一個預先設定的範本尚未涵蓋）建立範本。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-170">For example, you can create a template for your business process control, or a template for a regional data protection or compliance standard that isn’t covered by one of the pre-configured templates.</span></span>  <span data-ttu-id="9d7b8-171">透過建立您自己的範本，您可以建立自訂評估，以確保合規性分數不僅追蹤 Microsoft 雲端評估，也追蹤組織範圍內的任何其他風險評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-171">By creating your own templates, you can create custom assessments to ensure that Compliance Score tracks not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

<span data-ttu-id="9d7b8-172">您可以複製現有的範本或從 Excel 檔案中匯入控制項資訊，來建立新的範本。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-172">You can create new templates by copying an existing template, or by importing controls information from an Excel file.</span></span> <span data-ttu-id="9d7b8-173">查看[在合規性管理員中建立範本](working-with-compliance-manager.md#templates)的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-173">View detailed instructions for [creating templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

<span data-ttu-id="9d7b8-174">符合性分數的預先設定範本如下：</span><span class="sxs-lookup"><span data-stu-id="9d7b8-174">The pre-configured templates for Compliance Score are:</span></span>

1. [<span data-ttu-id="9d7b8-175">巴西一般資料保護法（LGPD）</span><span class="sxs-lookup"><span data-stu-id="9d7b8-175">Brazil General Data Protection Law (LGPD)</span></span>](https://go.microsoft.com/fwlink/?linkid=2115387)
2. <span data-ttu-id="9d7b8-176">[加州消費者隱私權法案（CCPA）](https://go.microsoft.com/fwlink/?linkid=2108871) （預覽）</span><span class="sxs-lookup"><span data-stu-id="9d7b8-176">[California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (Preview)</span></span>
3. [<span data-ttu-id="9d7b8-177">雲端安全性同盟（CSA） Cloud Controls 矩陣（CCM）3.0。1</span><span class="sxs-lookup"><span data-stu-id="9d7b8-177">Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1</span></span>](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [<span data-ttu-id="9d7b8-178">歐盟 GDPR</span><span class="sxs-lookup"><span data-stu-id="9d7b8-178">European Union GDPR</span></span>](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [<span data-ttu-id="9d7b8-179">聯邦金融機構檢查委員會（FFIEC）資訊安全性手冊</span><span class="sxs-lookup"><span data-stu-id="9d7b8-179">Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet</span></span>](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [<span data-ttu-id="9d7b8-180">FedRAMP 適中</span><span class="sxs-lookup"><span data-stu-id="9d7b8-180">FedRAMP Moderate</span></span>](https://go.microsoft.com/fwlink/?linkid=2108869)
7. <span data-ttu-id="9d7b8-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / 高[科技](https://go.microsoft.com/fwlink/?linkid=2109079)</span><span class="sxs-lookup"><span data-stu-id="9d7b8-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span></span>
8. <span data-ttu-id="9d7b8-182">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [澳大利亞政府版 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) （預覽）</span><span class="sxs-lookup"><span data-stu-id="9d7b8-182">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [Australian Government ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (Preview)</span></span>
9. [<span data-ttu-id="9d7b8-183">ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="9d7b8-183">ISO 27001:2013</span></span>](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [<span data-ttu-id="9d7b8-184">ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="9d7b8-184">ISO 27018:2014</span></span>](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [<span data-ttu-id="9d7b8-185">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="9d7b8-185">ISO 27701:2019</span></span>](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [<span data-ttu-id="9d7b8-186">Microsoft 365 資料保護基準</span><span class="sxs-lookup"><span data-stu-id="9d7b8-186">Microsoft 365 Data Protection Baseline</span></span>](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [<span data-ttu-id="9d7b8-187">NIST 800-53 Rev 4</span><span class="sxs-lookup"><span data-stu-id="9d7b8-187">NIST 800-53 Rev. 4</span></span>](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [<span data-ttu-id="9d7b8-188">NIST 800-171</span><span class="sxs-lookup"><span data-stu-id="9d7b8-188">NIST 800-171</span></span>](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [<span data-ttu-id="9d7b8-189">NIST Cybersecurity Framework （CSF）</span><span class="sxs-lookup"><span data-stu-id="9d7b8-189">NIST Cybersecurity Framework (CSF)</span></span>](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [<span data-ttu-id="9d7b8-190">SOC 1</span><span class="sxs-lookup"><span data-stu-id="9d7b8-190">SOC 1</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [<span data-ttu-id="9d7b8-191">SOC 2</span><span class="sxs-lookup"><span data-stu-id="9d7b8-191">SOC 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)

> [!NOTE]
> <span data-ttu-id="9d7b8-192">在公開預覽期間，請移至 [合規性管理員] 以建立及管理您的範本。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-192">During public preview, go to Compliance Manager to create and manage your templates.</span></span>

### <a name="groups"></a><span data-ttu-id="9d7b8-193">群組</span><span class="sxs-lookup"><span data-stu-id="9d7b8-193">Groups</span></span>

<span data-ttu-id="9d7b8-194">群組可讓您以合理的方式組織評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-194">Groups allow you to organize assessments in a way that is logical to you.</span></span> <span data-ttu-id="9d7b8-195">例如，您可以選擇依年、符合標準、服務、組織內的小組或其他方式來群組評估。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-195">For example, you may choose to group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span>

<span data-ttu-id="9d7b8-196">當相同群組中的兩個不同評估共用客戶管理的動作時，一個評估中的動作的執行詳細資料、測試及狀態，會自動同步處理至群組中任何其他評估中的相同動作。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-196">When two different assessments in the same group share customer-managed actions, the completion of implementation details, testing, and status for the action in one assessment automatically synchronizes to the same action in any other assessment in the group.</span></span> <span data-ttu-id="9d7b8-197">這會將指派的「改進」動作統一到群組中，並減少重複的工作。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-197">This unifies the assigned improvement actions across the group and reduces duplicating work.</span></span>

<span data-ttu-id="9d7b8-198">瞭解如何[在合規性管理員中建立群組](working-with-compliance-manager.md#groups)。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-198">Learn how to [create groups in Compliance Manager](working-with-compliance-manager.md#groups).</span></span> <span data-ttu-id="9d7b8-199">一旦您建立群組，您就可以[篩選「合規性分數」儀表板](compliance-score-setup.md#filtering-your-dashboard-view)，以查看一或多個群組的分數。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-199">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

## <a name="next-step-begin-setup"></a><span data-ttu-id="9d7b8-200">後續步驟：開始安裝程式</span><span class="sxs-lookup"><span data-stu-id="9d7b8-200">Next step: begin setup</span></span>

<span data-ttu-id="9d7b8-201">瞭解如何登入、設定許可權，以及設定[相容性分數設定](compliance-score-setup.md)的更新及儀表板視圖。</span><span class="sxs-lookup"><span data-stu-id="9d7b8-201">Learn how to sign in, set up permissions, and configure updates and dashboard views at [Compliance Score setup](compliance-score-setup.md).</span></span>
