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
ms.openlocfilehash: 5fced1a9452f2345a678bfef670e1a19b9811e81
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140848"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="7278a-103">Microsoft 合規性分數（預覽）</span><span class="sxs-lookup"><span data-stu-id="7278a-103">Microsoft Compliance Score (preview)</span></span>

<span data-ttu-id="7278a-104">[Microsoft 合規性分數](https://compliance.microsoft.com/compliancescore)可協助您簡化管理法規遵從性的方式，並透過方便使用的經驗降低法規遵從性風險。</span><span class="sxs-lookup"><span data-stu-id="7278a-104">[Microsoft Compliance Score](https://compliance.microsoft.com/compliancescore) helps to simplify the way you manage compliance and reduce compliance risks through a user-friendly experience.</span></span> <span data-ttu-id="7278a-105">[Microsoft 365 規範中心](microsoft-365-compliance-center.md)內的公開預覽適用的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="7278a-105">Compliance Score is available for public preview in the  [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>

<span data-ttu-id="7278a-106">**本文內容：** 請閱讀本文，以瞭解哪些相容性分數，以及如何為您的組織設定。</span><span class="sxs-lookup"><span data-stu-id="7278a-106">**In this article:** Read this article to understand what Compliance Score is and how to set it up for your organization.</span></span>

<span data-ttu-id="7278a-107">**深入瞭解更新：** 我們已于2020年4月發佈數個更新。</span><span class="sxs-lookup"><span data-stu-id="7278a-107">**Learn about updates:** We published several updates in the April 2020 release.</span></span> <span data-ttu-id="7278a-108">請造訪「[合規性分數版本](compliance-score-release-notes.md)資訊」，以查看「預覽」版本的合規性分數的新功能和已知問題。</span><span class="sxs-lookup"><span data-stu-id="7278a-108">Visit the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new and known issues with the preview version of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="7278a-109">合規性分數為何</span><span class="sxs-lookup"><span data-stu-id="7278a-109">What is Compliance Score</span></span>

<span data-ttu-id="7278a-110">Microsoft 合規性分數是 Microsoft 365 規範中心的預覽功能，可協助您瞭解組織的合規性狀況。</span><span class="sxs-lookup"><span data-stu-id="7278a-110">Microsoft Compliance Score is a preview feature in the Microsoft 365 compliance center to help you understand your organization's compliance posture.</span></span> <span data-ttu-id="7278a-111">它會計算以風險為基礎的分數，用以衡量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。</span><span class="sxs-lookup"><span data-stu-id="7278a-111">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="7278a-112">您可以使用合規性分數做為工具，以追蹤所有風險評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-112">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="7278a-113">它提供工作流程功能，協助您透過一般工具，有效地完成風險評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-113">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="7278a-114">如果您目前使用[合規性管理員](compliance-manager-overview.md)，您會注意到「合規性分數」現在是獨立的功能，具有更簡單且便於使用的設計，可協助您更輕鬆地管理規範。</span><span class="sxs-lookup"><span data-stu-id="7278a-114">If you currently use [Compliance Manager](compliance-manager-overview.md), you'll notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help you manage compliance more easily.</span></span> 

<span data-ttu-id="7278a-115">主要合規性分數頁面是您的自訂儀表板。</span><span class="sxs-lookup"><span data-stu-id="7278a-115">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="7278a-116">它會顯示您目前的評分，協助您瞭解需要注意的事項，並指導您採取動作以提升您的分數。</span><span class="sxs-lookup"><span data-stu-id="7278a-116">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="7278a-117">您的合規性分數儀表板看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="7278a-117">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="7278a-118">![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="7278a-118">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="7278a-119">簡化的規範管理</span><span class="sxs-lookup"><span data-stu-id="7278a-119">Simplified compliance management</span></span>

<span data-ttu-id="7278a-120">合規性分數可提供下列功能，以簡化規範管理：</span><span class="sxs-lookup"><span data-stu-id="7278a-120">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="7278a-121">**連續評估**：自動掃描您的 Microsoft 365 環境，以偵測和監視系統中資料保護控制項的效能</span><span class="sxs-lookup"><span data-stu-id="7278a-121">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="7278a-122">**建議的動作**：提供建議，並逐步指導您如何執行控制以最大化排名</span><span class="sxs-lookup"><span data-stu-id="7278a-122">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="7278a-123">**內建的控制項對應**：透過提供內建的共同作業架構，協助您在不斷提高的規範環境中保持最新狀態</span><span class="sxs-lookup"><span data-stu-id="7278a-123">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7278a-124">您不應將「合規性分數」和「合規性管理員」中的建議視為合規性的保證。</span><span class="sxs-lookup"><span data-stu-id="7278a-124">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="7278a-125">您可以根據法規環境評估和驗證客戶控制措施的效能。</span><span class="sxs-lookup"><span data-stu-id="7278a-125">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="7278a-126">這些服務目前是在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。</span><span class="sxs-lookup"><span data-stu-id="7278a-126">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="7278a-127">另請參閱[Microsoft 365 授權指南以取得安全性和合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="7278a-127">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="7278a-128">與合規性管理員的關係</span><span class="sxs-lookup"><span data-stu-id="7278a-128">Relationship to Compliance Manager</span></span>

<span data-ttu-id="7278a-129">請將合規性分數視為合規性管理員簡化版本。</span><span class="sxs-lookup"><span data-stu-id="7278a-129">Think of Compliance Score as a simplified version of Compliance Manager.</span></span> <span data-ttu-id="7278a-130">雖然這兩者都存在於不同的整合式工具中，但遵從性分數可讓您更容易監視整體的相容性狀況，並採取步驟加以改善。</span><span class="sxs-lookup"><span data-stu-id="7278a-130">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="7278a-131">合規性分數與合規性管理員共用相同的後端，所以合規性管理員中您可能已具備的任何資料都會以相容性分數顯示。</span><span class="sxs-lookup"><span data-stu-id="7278a-131">Compliance Score shares the same backend with Compliance Manager, so any data you may already have in Compliance Manager will show in Compliance Score.</span></span>

<span data-ttu-id="7278a-132">在公開預覽期間，有些功能會維持在合規性管理員內，例如管理評估和建立範本。</span><span class="sxs-lookup"><span data-stu-id="7278a-132">Some functionality remains solely in Compliance Manager during public preview, such as managing assessments and creating templates.</span></span> <span data-ttu-id="7278a-133">建議您在合規性分數中開始所有符合性管理活動。</span><span class="sxs-lookup"><span data-stu-id="7278a-133">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="7278a-134">當您接觸合規性管理員所處理的功能時，系統會將您導向該工具。</span><span class="sxs-lookup"><span data-stu-id="7278a-134">When you come to functions handled by Compliance Manager, you'll be guided to that tool.</span></span> <span data-ttu-id="7278a-135">基於此原因，本文中的一些檔會將您導向合規性管理員主題。</span><span class="sxs-lookup"><span data-stu-id="7278a-135">For that reason, some of this documentation directs you to Compliance Manager topics.</span></span>

<span data-ttu-id="7278a-136">深入瞭解[合規性分數版本附注](compliance-score-release-notes.md)中的合規性分數和合規性管理員之間的關係。</span><span class="sxs-lookup"><span data-stu-id="7278a-136">Learn more about the relationship between Compliance Score and Compliance Manager in the [Compliance Score release notes](compliance-score-release-notes.md).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="7278a-137">瞭解您的分數</span><span class="sxs-lookup"><span data-stu-id="7278a-137">Understanding your score</span></span>

<span data-ttu-id="7278a-138">合規性分數為您提供以 Microsoft 365 資料保護基準為基礎的初始分數。</span><span class="sxs-lookup"><span data-stu-id="7278a-138">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="7278a-139">此基準是一組包含常見業界法規和標準的控制。</span><span class="sxs-lookup"><span data-stu-id="7278a-139">This baseline is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="7278a-140">雖然這個分數是評估符合性狀況的好開端，但一旦您新增了與貴組織更為相關的評估，就會變得更強大。</span><span class="sxs-lookup"><span data-stu-id="7278a-140">While this score is a good starting point for assessing your compliance posture, Compliance Score becomes more powerful once you add assessments that are more relevant to your organization.</span></span>

<span data-ttu-id="7278a-141">例如，如果您的組織屬於金融服務行業，您可能會想要新增 FFIEC 評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-141">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="7278a-142">如果您的組織屬於醫療保健行業，您可以新增 HIPAA/高科技評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-142">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span> <span data-ttu-id="7278a-143">瞭解如何[在合規性管理員中新增評估](working-with-compliance-manager.md#assessments)。</span><span class="sxs-lookup"><span data-stu-id="7278a-143">Learn how to [add assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

<span data-ttu-id="7278a-144">深入瞭解[如何計算和持續監控規範分數](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="7278a-144">Learn more about [how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>


## <a name="key-components-controls-assessments-templates-groups"></a><span data-ttu-id="7278a-145">主要元件：控制項、評估、範本、群組</span><span class="sxs-lookup"><span data-stu-id="7278a-145">Key components: controls, assessments, templates, groups</span></span>

<span data-ttu-id="7278a-146">合規性分數使用多個元件，協助您管理相容性活動。</span><span class="sxs-lookup"><span data-stu-id="7278a-146">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="7278a-147">當您使用相容性分數指派、測試及監視合規性活動時，對重要元件有基本的瞭解是很有説明的：控制項、評估、範本和群組。</span><span class="sxs-lookup"><span data-stu-id="7278a-147">As you use Compliance Score to assign, test, and monitor compliance activities, it's helpful to have a basic understanding of the key components: controls, assessments, templates, and groups.</span></span>

### <a name="controls"></a><span data-ttu-id="7278a-148">控制項</span><span class="sxs-lookup"><span data-stu-id="7278a-148">Controls</span></span>

<span data-ttu-id="7278a-149">控制項定義如何評估和管理系統設定、組織程式，以及負責滿足法規、標準或內部原則的特定需求的人員。</span><span class="sxs-lookup"><span data-stu-id="7278a-149">A control defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or internal policy.</span></span>

<span data-ttu-id="7278a-150">合規性分數追蹤兩種類型的控制項：</span><span class="sxs-lookup"><span data-stu-id="7278a-150">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="7278a-151">**Microsoft 受管理的控制項**： microsoft cloud services 的控制項，microsoft 負責執行這種服務</span><span class="sxs-lookup"><span data-stu-id="7278a-151">**Microsoft-managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="7278a-152">**客戶管理的控制項**：由您的組織管理的控制項，由您負責執行</span><span class="sxs-lookup"><span data-stu-id="7278a-152">**Customer-managed controls**: controls managed by your organization, which you're responsible for implementing</span></span>
 
### <a name="assessments"></a><span data-ttu-id="7278a-153">評估</span><span class="sxs-lookup"><span data-stu-id="7278a-153">Assessments</span></span>

<span data-ttu-id="7278a-154">評估是一項範本評估，可對您的組織發起計分程式。</span><span class="sxs-lookup"><span data-stu-id="7278a-154">An assessment is an evaluation of a template that initiates the scoring process for your organization.</span></span> <span data-ttu-id="7278a-155">評估群組符合標準、法規或法律需求所需的動作。</span><span class="sxs-lookup"><span data-stu-id="7278a-155">Assessments group the actions necessary to meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="7278a-156">例如，您可能會有一個評估，當您完成其中的所有動作時，您的 Office 365 設定會以 ISO 27001 的需求為依據。</span><span class="sxs-lookup"><span data-stu-id="7278a-156">For example, you may have an assessment that, when you complete all actions within it, brings your Office 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="7278a-157">合規性分數為您的組織提供以 Microsoft 365 資料保護基準為基礎的初始評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-157">Compliance Score provides your organization with an initial assessment based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="7278a-158">這種評估是降低資料保護和合規性風險的建議（[深入瞭解](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）。</span><span class="sxs-lookup"><span data-stu-id="7278a-158">This assessment is a recommendation for reducing your data protection and compliance risks ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

<span data-ttu-id="7278a-159">評估包含數個元件：</span><span class="sxs-lookup"><span data-stu-id="7278a-159">Assessments have several components:</span></span>

- <span data-ttu-id="7278a-160">**範圍內的服務**：適用于評估的特定 Microsoft 服務集合</span><span class="sxs-lookup"><span data-stu-id="7278a-160">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="7278a-161">**Microsoft 管理控制項**： microsoft 所實施及測試的控制項</span><span class="sxs-lookup"><span data-stu-id="7278a-161">**Microsoft-managed controls**: controls that Microsoft implemented and tested</span></span>
- <span data-ttu-id="7278a-162">**客戶管理的控制項**：您管理的控制項</span><span class="sxs-lookup"><span data-stu-id="7278a-162">**Customer-managed controls**: controls that you manage</span></span>
- <span data-ttu-id="7278a-163">**評估分數**：完成該評估中的動作可取得的點數百分比</span><span class="sxs-lookup"><span data-stu-id="7278a-163">**Assessment score**: the percentage of the points achieved by completing actions within that assessment</span></span>

> [!NOTE]
> <span data-ttu-id="7278a-164">合規性分數會顯示您的評估，以及它們如何影響您的整體分數。</span><span class="sxs-lookup"><span data-stu-id="7278a-164">Compliance Score displays your assessments and how they factor into your overall score.</span></span> <span data-ttu-id="7278a-165">不過，在公開預覽期間，系統會將您導向合規性管理員以管理評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-165">However, during public preview you will be directed to Compliance Manager to manage your assessments.</span></span>

<span data-ttu-id="7278a-166">[在合規性管理員中查看管理評估](working-with-compliance-manager.md#assessments)的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="7278a-166">View detailed instructions for [managing assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

### <a name="templates"></a><span data-ttu-id="7278a-167">範本</span><span class="sxs-lookup"><span data-stu-id="7278a-167">Templates</span></span>

<span data-ttu-id="7278a-168">合規性分數可提供預先設定的範本進行評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-168">Compliance Score provides pre-configured templates for assessments.</span></span> <span data-ttu-id="7278a-169">您也可以將自己的控制項和動作新增至預先設定的範本，以建立自訂評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-169">You can also create a Custom Assessment by adding your own controls and actions to a pre-configured template.</span></span> <span data-ttu-id="7278a-170">例如，您可以為商務程式控制建立範本，或為區域資料保護或符合性標準（其中一個預先設定的範本尚未涵蓋）建立範本。</span><span class="sxs-lookup"><span data-stu-id="7278a-170">For example, you can create a template for your business process control, or a template for a regional data protection or compliance standard that isn't covered by one of the pre-configured templates.</span></span> <span data-ttu-id="7278a-171">透過將您自己的範本引入合規性分數，您不僅可以追蹤 Microsoft 雲端評估，還可以追蹤組織範圍內任何其他風險評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-171">By bringing your own templates into Compliance Score, you can track not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

<span data-ttu-id="7278a-172">符合性分數的預先設定範本如下：</span><span class="sxs-lookup"><span data-stu-id="7278a-172">The pre-configured templates for Compliance Score are:</span></span>

1. [<span data-ttu-id="7278a-173">巴西一般資料保護法（LGPD）</span><span class="sxs-lookup"><span data-stu-id="7278a-173">Brazil General Data Protection Law (LGPD)</span></span>](https://go.microsoft.com/fwlink/?linkid=2115387)
2. <span data-ttu-id="7278a-174">[加州消費者隱私權法案（CCPA）](https://go.microsoft.com/fwlink/?linkid=2108871) （預覽）</span><span class="sxs-lookup"><span data-stu-id="7278a-174">[California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (preview)</span></span>
3. [<span data-ttu-id="7278a-175">雲端安全性同盟（CSA） Cloud Controls 矩陣（CCM）3.0。1</span><span class="sxs-lookup"><span data-stu-id="7278a-175">Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1</span></span>](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [<span data-ttu-id="7278a-176">歐盟 GDPR</span><span class="sxs-lookup"><span data-stu-id="7278a-176">European Union GDPR</span></span>](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [<span data-ttu-id="7278a-177">聯邦金融機構檢查委員會（FFIEC）資訊安全性手冊</span><span class="sxs-lookup"><span data-stu-id="7278a-177">Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet</span></span>](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [<span data-ttu-id="7278a-178">FedRAMP 適中</span><span class="sxs-lookup"><span data-stu-id="7278a-178">FedRAMP Moderate</span></span>](https://go.microsoft.com/fwlink/?linkid=2108869)
7. <span data-ttu-id="7278a-179">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / 高[科技](https://go.microsoft.com/fwlink/?linkid=2109079)</span><span class="sxs-lookup"><span data-stu-id="7278a-179">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span></span>
8. <span data-ttu-id="7278a-180">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [澳大利亞政府版 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) （預覽）</span><span class="sxs-lookup"><span data-stu-id="7278a-180">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [Australian Government ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (preview)</span></span>
9. [<span data-ttu-id="7278a-181">ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="7278a-181">ISO 27001:2013</span></span>](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [<span data-ttu-id="7278a-182">ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="7278a-182">ISO 27018:2014</span></span>](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [<span data-ttu-id="7278a-183">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="7278a-183">ISO 27701:2019</span></span>](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [<span data-ttu-id="7278a-184">Microsoft 365 資料保護基準</span><span class="sxs-lookup"><span data-stu-id="7278a-184">Microsoft 365 Data Protection Baseline</span></span>](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [<span data-ttu-id="7278a-185">NIST 800-53 Rev 4</span><span class="sxs-lookup"><span data-stu-id="7278a-185">NIST 800-53 Rev. 4</span></span>](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [<span data-ttu-id="7278a-186">NIST 800-171</span><span class="sxs-lookup"><span data-stu-id="7278a-186">NIST 800-171</span></span>](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [<span data-ttu-id="7278a-187">NIST Cybersecurity Framework （CSF）</span><span class="sxs-lookup"><span data-stu-id="7278a-187">NIST Cybersecurity Framework (CSF)</span></span>](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [<span data-ttu-id="7278a-188">SOC 1</span><span class="sxs-lookup"><span data-stu-id="7278a-188">SOC 1</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [<span data-ttu-id="7278a-189">SOC 2</span><span class="sxs-lookup"><span data-stu-id="7278a-189">SOC 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)

<span data-ttu-id="7278a-190">針對在合規性管理員中所進行的範本，查看[建立範本的詳細指示](working-with-compliance-manager.md#templates)。</span><span class="sxs-lookup"><span data-stu-id="7278a-190">View [detailed instructions for creating templates](working-with-compliance-manager.md#templates), which occurs in Compliance Manager.</span></span>

### <a name="groups"></a><span data-ttu-id="7278a-191">群組</span><span class="sxs-lookup"><span data-stu-id="7278a-191">Groups</span></span>

<span data-ttu-id="7278a-192">群組可讓您以合理的方式組織評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-192">Groups allow you to organize assessments in a way that is logical to you.</span></span> <span data-ttu-id="7278a-193">例如，您可以選擇依年、符合標準、服務、組織內的小組或其他方式來群組評估。</span><span class="sxs-lookup"><span data-stu-id="7278a-193">For example, you may choose to group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span>

<span data-ttu-id="7278a-194">當同一個群組中的兩個不同評估共用客戶管理的動作時，在一個評估中對該動作執行詳細資料、測試及狀態所做的更新，會自動同步處理至群組中任何其他評估中的相同動作。</span><span class="sxs-lookup"><span data-stu-id="7278a-194">When two different assessments in the same group share customer-managed actions, updates you make to the implementation details, testing, and status for the action in one assessment will automatically synchronize to the same action in any other assessment in the group.</span></span> <span data-ttu-id="7278a-195">以這種方式同步處理動作會使指派的「改進」動作統一整個群組，並減少重複的工作。</span><span class="sxs-lookup"><span data-stu-id="7278a-195">Synching actions in this way unifies the assigned improvement actions across the group and reduces duplicating work.</span></span>

<span data-ttu-id="7278a-196">瞭解如何[在合規性管理員中建立群組](working-with-compliance-manager.md#groups)。</span><span class="sxs-lookup"><span data-stu-id="7278a-196">Learn how to [create groups in Compliance Manager](working-with-compliance-manager.md#groups).</span></span> <span data-ttu-id="7278a-197">一旦您建立群組，您就可以[篩選「合規性分數」儀表板](compliance-score-setup.md#filtering-your-dashboard-view)，以查看一或多個群組的分數。</span><span class="sxs-lookup"><span data-stu-id="7278a-197">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

## <a name="next-step-begin-setup"></a><span data-ttu-id="7278a-198">後續步驟：開始安裝程式</span><span class="sxs-lookup"><span data-stu-id="7278a-198">Next step: begin setup</span></span>

<span data-ttu-id="7278a-199">瞭解如何登入、設定許可權，以及設定[相容性分數設定](compliance-score-setup.md)的更新及儀表板視圖。</span><span class="sxs-lookup"><span data-stu-id="7278a-199">Learn how to sign in, set up permissions, and configure updates and dashboard views at [Compliance Score setup](compliance-score-setup.md).</span></span>
