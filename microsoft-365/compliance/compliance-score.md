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
description: Microsoft 合規性分數可幫助組織簡化和自動化的風險評估，並建議建議的動作，以協助地址的風險。
ms.openlocfilehash: c1f912deacd9e7a9b30cbc4665a259177aeebf65
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595740"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="7f96c-103">Microsoft 合規性分數 （預覽）</span><span class="sxs-lookup"><span data-stu-id="7f96c-103">Microsoft Compliance Score (Preview)</span></span>

<span data-ttu-id="7f96c-104">Microsoft 合規性分數可協助簡化管理合規性，並減少透過方便使用經驗的合規性風險的方式。</span><span class="sxs-lookup"><span data-stu-id="7f96c-104">Microsoft Compliance Score helps to simplify the way you manage compliance and reduce compliance risks through a user-friendly experience.</span></span> <span data-ttu-id="7f96c-105">合規性分數是現在適用於[Microsoft 365 合規性中心](microsoft-365-compliance-center.md)中公開預覽。</span><span class="sxs-lookup"><span data-stu-id="7f96c-105">Compliance Score is now available for public preview in the  [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>

<span data-ttu-id="7f96c-106">**本文中：** 閱讀本篇文章以了解合規性分數是什麼以及如何設定以為組織。</span><span class="sxs-lookup"><span data-stu-id="7f96c-106">**In this article:** Read this article to understand what Compliance Score is and how to set it up for your organization.</span></span>

<span data-ttu-id="7f96c-107">**了解如何更新：** 移至[合規性分數版本資訊](compliance-score-release-notes.md)請參閱什麼是新的和已知問題與合規性分數的預覽版本。</span><span class="sxs-lookup"><span data-stu-id="7f96c-107">**Learn about updates:** Go to the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new and known issues with the preview version of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="7f96c-108">合規性分數是什麼</span><span class="sxs-lookup"><span data-stu-id="7f96c-108">What is Compliance Score</span></span>

<span data-ttu-id="7f96c-109">Microsoft 合規性分數是在 Microsoft 365 合規性中心，以協助您了解貴組織的合規性狀態的預覽功能。</span><span class="sxs-lookup"><span data-stu-id="7f96c-109">Microsoft Compliance Score is a preview feature in the Microsoft 365 compliance center to help you understand your organization’s compliance posture.</span></span> <span data-ttu-id="7f96c-110">它會計算測量中完成協助減少資料保護和法規的標準周圍的風險的動作您進行風險分數。</span><span class="sxs-lookup"><span data-stu-id="7f96c-110">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="7f96c-111">您可以使用合規性分數做為工具，以追蹤所有風險評定。</span><span class="sxs-lookup"><span data-stu-id="7f96c-111">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="7f96c-112">它提供可協助您有效率地完成您透過一般工具的風險評估工作流程功能。</span><span class="sxs-lookup"><span data-stu-id="7f96c-112">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="7f96c-113">如果您目前使用[合規性管理員中](compliance-manager-overview.md)，您會注意到合規性分數現在是獨立功能與更簡單，更方便使用的設計，可協助您更輕鬆地管理合規性。</span><span class="sxs-lookup"><span data-stu-id="7f96c-113">If you currently use [Compliance Manager](compliance-manager-overview.md), you’ll notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help you manage compliance more easily.</span></span> 

<span data-ttu-id="7f96c-114">主要的合規性分數頁面是自訂儀表板。</span><span class="sxs-lookup"><span data-stu-id="7f96c-114">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="7f96c-115">它會顯示您目前的分數、 可協助您查看哪些需要注意，及引導您以動作，以改善您的分數。</span><span class="sxs-lookup"><span data-stu-id="7f96c-115">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="7f96c-116">合規性分數儀表板看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="7f96c-116">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="7f96c-117">![合規性分數-儀表板](media/compliance-score-dashboard.png "合規性分數儀表板")</span><span class="sxs-lookup"><span data-stu-id="7f96c-117">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="7f96c-118">簡化的合規性管理</span><span class="sxs-lookup"><span data-stu-id="7f96c-118">Simplified compliance management</span></span>

<span data-ttu-id="7f96c-119">合規性分數可協助簡化相符性管理提供：</span><span class="sxs-lookup"><span data-stu-id="7f96c-119">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="7f96c-120">**連續評估**： 自動透過您的 Microsoft 365 環境，以偵測並監視您的系統中的資料保護控制項的效率掃描</span><span class="sxs-lookup"><span data-stu-id="7f96c-120">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="7f96c-121">**建議的動作**： 提供建議和如何實作控制項的逐步指引，以最大化您的分數</span><span class="sxs-lookup"><span data-stu-id="7f96c-121">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="7f96c-122">**內建控制項的對應**： 協助您保持最新的不斷變化的合規性橫向藉由提供內建的通用控制項架構</span><span class="sxs-lookup"><span data-stu-id="7f96c-122">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="7f96c-123">合規性分數不 express 與任何特定的標準或法規的組織符合性絕對量值。</span><span class="sxs-lookup"><span data-stu-id="7f96c-123">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="7f96c-124">它來表示您要採用的個人資料和個人隱私權降低風險的控制項的程度。</span><span class="sxs-lookup"><span data-stu-id="7f96c-124">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="7f96c-125">合規性分數和合規性管理員中的建議事項不應該解譯成保證郵件可以合規性。</span><span class="sxs-lookup"><span data-stu-id="7f96c-125">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="7f96c-126">這項服務目前處於預覽狀態，並受限於條款和條件[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中。</span><span class="sxs-lookup"><span data-stu-id="7f96c-126">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="7f96c-127">關聯到合規性管理員</span><span class="sxs-lookup"><span data-stu-id="7f96c-127">Relationship to Compliance Manager</span></span>

<span data-ttu-id="7f96c-128">將視為的簡化版合規性管理員的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="7f96c-128">Think of Compliance Score as a simplified version of Compliance Manager.</span></span> <span data-ttu-id="7f96c-129">雖然這兩個存在於不同尚未整合式工具，合規性分數容易監視您的整體合規性狀態，並採取步驟來改善它。</span><span class="sxs-lookup"><span data-stu-id="7f96c-129">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="7f96c-130">合規性分數共用相同的後端與合規性管理員中，因此您可能已經有合規性管理員中的任何資料將會顯示在 [合規性分數。</span><span class="sxs-lookup"><span data-stu-id="7f96c-130">Compliance Score shares the same backend with Compliance Manager, so any data you may already have in Compliance Manager will show in Compliance Score.</span></span>

<span data-ttu-id="7f96c-131">期間公開預覽版，某些功能會維持察覺合規性管理員中，例如管理的評估和建立範本。</span><span class="sxs-lookup"><span data-stu-id="7f96c-131">During public preview, some functionality remains solely in Compliance Manager, such as managing assessments and creating templates.</span></span> <span data-ttu-id="7f96c-132">建議開始所有您合規性管理中的活動合規性分數。</span><span class="sxs-lookup"><span data-stu-id="7f96c-132">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="7f96c-133">當您回到函式處理由合規性管理員中時，您將會引導該工具。</span><span class="sxs-lookup"><span data-stu-id="7f96c-133">When you come to functions handled by Compliance Manager, you will be guided to that tool.</span></span> <span data-ttu-id="7f96c-134">基於這個理由，部分這份文件會引導您合規性管理員中的主題。</span><span class="sxs-lookup"><span data-stu-id="7f96c-134">For that reason, some of this documentation directs you to Compliance Manager topics.</span></span>

<span data-ttu-id="7f96c-135">深入了解合規性分數與[合規性分數版本資訊](compliance-score-release-notes.md)中的合規性管理員之間的關係。</span><span class="sxs-lookup"><span data-stu-id="7f96c-135">Learn more about the relationship between Compliance Score and Compliance Manager in the [Compliance Score release notes](compliance-score-release-notes.md).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="7f96c-136">了解您的分數</span><span class="sxs-lookup"><span data-stu-id="7f96c-136">Understanding your score</span></span>

<span data-ttu-id="7f96c-137">合規性分數可讓您根據 Microsoft 365 的資料保護基準初始分數。</span><span class="sxs-lookup"><span data-stu-id="7f96c-137">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="7f96c-138">此基準線是一組控制項包含一般產業法規及標準。</span><span class="sxs-lookup"><span data-stu-id="7f96c-138">This baseline is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="7f96c-139">雖然此分數是不錯的起點的評估您的合規性狀態，但合規性分數會變成功能更強大，一旦您新增至您的組織更相關的評估。</span><span class="sxs-lookup"><span data-stu-id="7f96c-139">While this score is a good starting point for assessing your compliance posture, Compliance Score becomes more powerful once you add assessments that are more relevant to your organization.</span></span>

<span data-ttu-id="7f96c-140">例如，如果您的組織屬於金融服務產業，可能會想要新增 FFIEC 評估。</span><span class="sxs-lookup"><span data-stu-id="7f96c-140">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="7f96c-141">如果您的組織屬於醫療保健產業，您可以新增 HIPAA/HITECH 評估。</span><span class="sxs-lookup"><span data-stu-id="7f96c-141">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span> <span data-ttu-id="7f96c-142">了解如何[新增評估合規性管理員中](working-with-compliance-manager.md#assessments)。</span><span class="sxs-lookup"><span data-stu-id="7f96c-142">Learn how to [add assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

<span data-ttu-id="7f96c-143">深入了[解您的合規性分數是計算](compliance-score-methodology.md)和持續受到監視。</span><span class="sxs-lookup"><span data-stu-id="7f96c-143">Learn more about [how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>


## <a name="key-components-controls-assessments-templates-groups"></a><span data-ttu-id="7f96c-144">主要元件： 控制項、 評估、 範本、 群組</span><span class="sxs-lookup"><span data-stu-id="7f96c-144">Key components: controls, assessments, templates, groups</span></span>

<span data-ttu-id="7f96c-145">合規性分數會使用數個元件，可協助您管理您的合規性活動。</span><span class="sxs-lookup"><span data-stu-id="7f96c-145">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="7f96c-146">當您可以使用合規性分數指派、 測試和監視合規性活動，很有幫助有基本了解這些重要元件。</span><span class="sxs-lookup"><span data-stu-id="7f96c-146">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of these key components.</span></span> <span data-ttu-id="7f96c-147">此圖顯示它們之間的關係：</span><span class="sxs-lookup"><span data-stu-id="7f96c-147">This diagram shows the relationships among them:</span></span>

<span data-ttu-id="7f96c-148">![合規性管理員第 3 版中的關聯性](media/compliance-manager-relationships.png "合規性分數元件")</span><span class="sxs-lookup"><span data-stu-id="7f96c-148">![Relationships in Compliance Manager Version 3](media/compliance-manager-relationships.png "Compliance Score components")</span></span>

### <a name="controls"></a><span data-ttu-id="7f96c-149">控制項</span><span class="sxs-lookup"><span data-stu-id="7f96c-149">Controls</span></span>

<span data-ttu-id="7f96c-150">控制項定義如何評估及管理系統組態，組織的程序，以符合規定，標準，或內部原則的特定需求的人員責任。</span><span class="sxs-lookup"><span data-stu-id="7f96c-150">A control defines how you assess and manage system configuration, organizational process, and people accountability to meet a specific requirement of a regulation, standard, or internal policy.</span></span>

<span data-ttu-id="7f96c-151">合規性分數追蹤兩種類型的控制項：</span><span class="sxs-lookup"><span data-stu-id="7f96c-151">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="7f96c-152">**Microsoft 管理控制措施**： 控制項的 Microsoft 雲端服務，Microsoft 是負責實作</span><span class="sxs-lookup"><span data-stu-id="7f96c-152">**Microsoft-managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="7f96c-153">**客戶管理控制措施**： 由您的組織，您必須負責實作受管理的控制項</span><span class="sxs-lookup"><span data-stu-id="7f96c-153">**Customer-managed controls**: controls managed by your organization, which you are responsible for implementing</span></span>
 
### <a name="assessments"></a><span data-ttu-id="7f96c-154">「 評估 」</span><span class="sxs-lookup"><span data-stu-id="7f96c-154">Assessments</span></span>

<span data-ttu-id="7f96c-155">評估是範本的用來評估的起始貴組織的計分程序。</span><span class="sxs-lookup"><span data-stu-id="7f96c-155">An assessment is an evaluation of a template that initiates the scoring process for your organization.</span></span> <span data-ttu-id="7f96c-156">評估群組以符合需求的標準、 規定或法律規定所需的動作。</span><span class="sxs-lookup"><span data-stu-id="7f96c-156">Assessments group the actions necessary to meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="7f96c-157">例如，您可能需要評估，當您完成所有動作內，將帶您的 Office 365 設定內嵌 ISO 27001 需求。</span><span class="sxs-lookup"><span data-stu-id="7f96c-157">For example, you may have an assessment that, when you complete all actions within it, brings your Office 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="7f96c-158">根據預設，合規性分數會提供根據 Microsoft 365 資料保護比較基準，建議減少 （[了解更多](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)） 您的資料保護和合規性風險評估您的組織。</span><span class="sxs-lookup"><span data-stu-id="7f96c-158">By default, Compliance Score provides your organization with an assessment based on the Microsoft 365 data protection baseline, a recommendation for reducing your data protection and compliance risks ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

<span data-ttu-id="7f96c-159">評估包含數個元件：</span><span class="sxs-lookup"><span data-stu-id="7f96c-159">Assessments include several components:</span></span>

- <span data-ttu-id="7f96c-160">**範圍內的服務**： 一組特定的 Microsoft 服務適用於評估</span><span class="sxs-lookup"><span data-stu-id="7f96c-160">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="7f96c-161">**Microsoft 管理控制措施**： Microsoft 實作和測試控制項</span><span class="sxs-lookup"><span data-stu-id="7f96c-161">**Microsoft-managed controls**: controls that Microsoft implemented and tested</span></span>
- <span data-ttu-id="7f96c-162">**客戶管理控制措施**： 您管理的控制項</span><span class="sxs-lookup"><span data-stu-id="7f96c-162">**Customer-managed controls**: controls that you manage</span></span>
- <span data-ttu-id="7f96c-163">**評估分數**： 達到完成動作內該評定的點的百分比</span><span class="sxs-lookup"><span data-stu-id="7f96c-163">**Assessment score**: the percentage of the points achieved by completing actions within that assessment</span></span>

> [!NOTE]
> <span data-ttu-id="7f96c-164">合規性分數會顯示您評估和他們因素入您的整體分數的方式。</span><span class="sxs-lookup"><span data-stu-id="7f96c-164">Compliance Score displays your assessments and how they factor into your overall score.</span></span> <span data-ttu-id="7f96c-165">不過，在公開預覽期間會將您導向到合規性管理員來管理您評估。</span><span class="sxs-lookup"><span data-stu-id="7f96c-165">However, during public preview you will be directed to Compliance Manager to manage your assessments.</span></span>

<span data-ttu-id="7f96c-166">檢視[使用評估合規性管理員中](working-with-compliance-manager.md#assessments)的詳細的指示。</span><span class="sxs-lookup"><span data-stu-id="7f96c-166">View detailed instructions for [working with assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

### <a name="templates"></a><span data-ttu-id="7f96c-167">範本</span><span class="sxs-lookup"><span data-stu-id="7f96c-167">Templates</span></span>

<span data-ttu-id="7f96c-168">合規性分數提供評估預先設定的範本。</span><span class="sxs-lookup"><span data-stu-id="7f96c-168">Compliance Score provides pre-configured templates for assessments.</span></span> <span data-ttu-id="7f96c-169">合規性分數也可讓您建立您自己的評估，以符合您需求的範本。</span><span class="sxs-lookup"><span data-stu-id="7f96c-169">Compliance Score also allows you to create templates for your own assessments to suit your needs.</span></span> <span data-ttu-id="7f96c-170">例如，您可以建立商務程序控制項、 範本或範本區域資料保護或合規性標準，未涵蓋的其中一個預先設定的範本。</span><span class="sxs-lookup"><span data-stu-id="7f96c-170">For example, you can create a template for your business process control, or a template for a regional data protection or compliance standard that isn’t covered by one of the pre-configured templates.</span></span>  <span data-ttu-id="7f96c-171">藉由建立您自己的範本，您可以建立自訂的評估，以確保合規性分數追蹤 Microsoft 雲端評估，不僅也任何其他的風險評估在貴組織的範圍內。</span><span class="sxs-lookup"><span data-stu-id="7f96c-171">By creating your own templates, you can create custom assessments to ensure that Compliance Score tracks not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

<span data-ttu-id="7f96c-172">藉由複製現有的範本，或由 Excel 檔案匯入控制項的資訊，您可以建立新的範本。</span><span class="sxs-lookup"><span data-stu-id="7f96c-172">You can create new templates by copying an existing template, or by importing controls information from an Excel file.</span></span> <span data-ttu-id="7f96c-173">檢視[建立範本合規性管理員中](working-with-compliance-manager.md#templates)的詳細的指示。</span><span class="sxs-lookup"><span data-stu-id="7f96c-173">View detailed instructions for [creating templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

<span data-ttu-id="7f96c-174">預先設定的範本的合規性分數是：</span><span class="sxs-lookup"><span data-stu-id="7f96c-174">The pre-configured templates for Compliance Score are:</span></span>

1. [<span data-ttu-id="7f96c-175">巴西一般資料保護 Law (LGPD)</span><span class="sxs-lookup"><span data-stu-id="7f96c-175">Brazil General Data Protection Law (LGPD)</span></span>](https://go.microsoft.com/fwlink/?linkid=2115387)
2. <span data-ttu-id="7f96c-176">[加州消費者隱私權法案 (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) （預覽）</span><span class="sxs-lookup"><span data-stu-id="7f96c-176">[California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (Preview)</span></span>
3. [<span data-ttu-id="7f96c-177">雲端安全聯盟 (CSA) 雲端控制項矩陣 (CCM) 3.0.1</span><span class="sxs-lookup"><span data-stu-id="7f96c-177">Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1</span></span>](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [<span data-ttu-id="7f96c-178">歐盟 GDPR</span><span class="sxs-lookup"><span data-stu-id="7f96c-178">European Union GDPR</span></span>](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [<span data-ttu-id="7f96c-179">聯邦金融機構檢查委員會 (FFIEC) 的資訊安全性手冊</span><span class="sxs-lookup"><span data-stu-id="7f96c-179">Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet</span></span>](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [<span data-ttu-id="7f96c-180">FedRAMP 中度</span><span class="sxs-lookup"><span data-stu-id="7f96c-180">FedRAMP Moderate</span></span>](https://go.microsoft.com/fwlink/?linkid=2108869)
7. <span data-ttu-id="7f96c-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span><span class="sxs-lookup"><span data-stu-id="7f96c-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span></span>
8. <span data-ttu-id="7f96c-182">[次](https://go.microsoft.com/fwlink/?linkid=2113709) / [澳洲政府 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) （預覽）</span><span class="sxs-lookup"><span data-stu-id="7f96c-182">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [Australian Government ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (Preview)</span></span>
9. [<span data-ttu-id="7f96c-183">ISO 27001: 2013</span><span class="sxs-lookup"><span data-stu-id="7f96c-183">ISO 27001:2013</span></span>](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [<span data-ttu-id="7f96c-184">ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="7f96c-184">ISO 27018:2014</span></span>](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [<span data-ttu-id="7f96c-185">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="7f96c-185">ISO 27701:2019</span></span>](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [<span data-ttu-id="7f96c-186">Microsoft 365 的資料保護基準</span><span class="sxs-lookup"><span data-stu-id="7f96c-186">Microsoft 365 Data Protection Baseline</span></span>](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [<span data-ttu-id="7f96c-187">NIST 800-53 修訂 4</span><span class="sxs-lookup"><span data-stu-id="7f96c-187">NIST 800-53 Rev. 4</span></span>](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [<span data-ttu-id="7f96c-188">NIST 800-171</span><span class="sxs-lookup"><span data-stu-id="7f96c-188">NIST 800-171</span></span>](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [<span data-ttu-id="7f96c-189">NIST Cybersecurity Framework (CSF)</span><span class="sxs-lookup"><span data-stu-id="7f96c-189">NIST Cybersecurity Framework (CSF)</span></span>](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [<span data-ttu-id="7f96c-190">SOC 1</span><span class="sxs-lookup"><span data-stu-id="7f96c-190">SOC 1</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [<span data-ttu-id="7f96c-191">SOC 2</span><span class="sxs-lookup"><span data-stu-id="7f96c-191">SOC 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)

> [!NOTE]
> <span data-ttu-id="7f96c-192">期間公開預覽，請移至合規性管理員中建立及管理自己的範本。</span><span class="sxs-lookup"><span data-stu-id="7f96c-192">During public preview, go to Compliance Manager to create and manage your templates.</span></span>

### <a name="groups"></a><span data-ttu-id="7f96c-193">群組</span><span class="sxs-lookup"><span data-stu-id="7f96c-193">Groups</span></span>

<span data-ttu-id="7f96c-194">群組可讓您組織的方式，是邏輯給您的評估。</span><span class="sxs-lookup"><span data-stu-id="7f96c-194">Groups allow you to organize assessments in a way that is logical to you.</span></span> <span data-ttu-id="7f96c-195">例如，您可以依年份，合規性標準，選擇群組評估服務，您的組織或其他方法中的 teams。</span><span class="sxs-lookup"><span data-stu-id="7f96c-195">For example, you may choose to group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span>

<span data-ttu-id="7f96c-196">當兩個不同的 「 評估 」 在相同的群組共用客戶管理動作時，完成的實作詳細資料、 測試和一個評估巨集指令的狀態會自動同步處理至群組中的任何其他評估中的相同動作。</span><span class="sxs-lookup"><span data-stu-id="7f96c-196">When two different assessments in the same group share customer-managed actions, the completion of implementation details, testing, and status for the action in one assessment automatically synchronizes to the same action in any other assessment in the group.</span></span> <span data-ttu-id="7f96c-197">此統整指派的改進動作跨群組，並減少複製的工作。</span><span class="sxs-lookup"><span data-stu-id="7f96c-197">This unifies the assigned improvement actions across the group and reduces duplicating work.</span></span>

<span data-ttu-id="7f96c-198">了解如何[建立群組合規性管理員中](working-with-compliance-manager.md#groups)。</span><span class="sxs-lookup"><span data-stu-id="7f96c-198">Learn how to [create groups in Compliance Manager](working-with-compliance-manager.md#groups).</span></span> <span data-ttu-id="7f96c-199">一旦您建立的群組，您可以[篩選您合規性分數儀表板](compliance-score-setup.md#filtering-your-dashboard-view)來檢視您的分數，由一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="7f96c-199">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

## <a name="next-step-begin-setup"></a><span data-ttu-id="7f96c-200">下一步： 開始安裝</span><span class="sxs-lookup"><span data-stu-id="7f96c-200">Next step: begin setup</span></span>

<span data-ttu-id="7f96c-201">了解如何登入，設定權限，以及在[合規性分數安裝](compliance-score-setup.md)設定更新及儀表板檢視。</span><span class="sxs-lookup"><span data-stu-id="7f96c-201">Learn how to sign in, set up permissions, and configure updates and dashboard views at [Compliance Score setup](compliance-score-setup.md).</span></span>
