---
title: 規劃資料遺失防護
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 資料遺失防護的規劃程式概述
ms.openlocfilehash: 6a72a8bab27db4d8b11d3e0b3d7a1dac7a1f0092
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52581586"
---
# <a name="plan-for-data-loss-prevention-dlp"></a><span data-ttu-id="2ded8-103">規劃資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="2ded8-103">Plan for data loss prevention (DLP)</span></span>

<span data-ttu-id="2ded8-104">每個組織會以不同的方式規劃及實施資料遺失防護 (DLP) ，因為每個組織的業務需求、目標、資源及情況都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2ded8-104">Every organization will plan for and implement data loss prevention (DLP) differently, because every organization's business needs, goals, resources, and situation are unique to them.</span></span> <span data-ttu-id="2ded8-105">不過，所有成功的 DLP 實現都有通用的元素。</span><span class="sxs-lookup"><span data-stu-id="2ded8-105">However, there are elements that are common to all successful DLP implementations.</span></span> <span data-ttu-id="2ded8-106">本文提供在其 DLP 規劃中組織所使用的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="2ded8-106">This article presents the best practices that are used by organizations in their DLP planning.</span></span>

## <a name="multiple-starting-points"></a><span data-ttu-id="2ded8-107">多個起始點</span><span class="sxs-lookup"><span data-stu-id="2ded8-107">Multiple starting points</span></span>

<span data-ttu-id="2ded8-108">許多組織會選擇實施 DLP，以遵守各種政府或工業規定。</span><span class="sxs-lookup"><span data-stu-id="2ded8-108">Many organizations choose to implement DLP to comply with various governmental or industry regulations.</span></span> <span data-ttu-id="2ded8-109">例如，歐盟的一般資料保護法規 (GDPR) ，或是健康保險業便攜性和責任法案 (HIPAA) 或加州消費者隱私權法案 (CCPA) 。</span><span class="sxs-lookup"><span data-stu-id="2ded8-109">For example, the European Union's General Data Protection Regulation (GDPR), or the Health Insurance Portability and Accountability Act (HIPAA), or the California Consumer Privacy Act (CCPA).</span></span> <span data-ttu-id="2ded8-110">他們也會執行資料遺失防護，以保護其智慧財產權。</span><span class="sxs-lookup"><span data-stu-id="2ded8-110">They also implement data loss prevention to protect their intellectual property.</span></span> <span data-ttu-id="2ded8-111">但 DLP 旅程中的開始位置和終極目的地各不相同。</span><span class="sxs-lookup"><span data-stu-id="2ded8-111">But the starting place and ultimate destination in the DLP journey vary.</span></span> 

<span data-ttu-id="2ded8-112">組織可以開始其 DLP 旅程：</span><span class="sxs-lookup"><span data-stu-id="2ded8-112">Organizations can start their DLP journey:</span></span>

- <span data-ttu-id="2ded8-113">從平臺焦點，像是在 Teams 聊天和通道郵件或 Windows 10 裝置上保護資訊的需要</span><span class="sxs-lookup"><span data-stu-id="2ded8-113">from a platform focus, like wanting to protect information in Teams Chat and Channel messages or on Windows 10 devices</span></span>
- <span data-ttu-id="2ded8-114">瞭解他們想要設定保護的敏感資訊，例如衛生護理記錄，並直接定義原則以加以保護</span><span class="sxs-lookup"><span data-stu-id="2ded8-114">knowing what sensitive information they want to prioritize protecting, like health care records, and going straight to defining policies to protect it</span></span>
- <span data-ttu-id="2ded8-115">不知道其機密資訊的所在位置，以及誰在什麼地方執行什麼，如此一來，他們就能發現和分類，並採取一種更具系統手段的方法。</span><span class="sxs-lookup"><span data-stu-id="2ded8-115">without knowing what their sensitive information is, where it is, and who is doing what with it so they start with discovery and categorization and take a more methodical approach</span></span>
- <span data-ttu-id="2ded8-116">不知道其機密資訊的來源或所在位置，或誰在做什麼，但他們會直接移動以定義原則，並使用這些結果作為開始地點，然後從那裡精煉其原則。</span><span class="sxs-lookup"><span data-stu-id="2ded8-116">without knowing what their sensitive information is, or where it is, or who is doing what with it, but they will move straight to defining policies and use those outcomes as a starting place and then refine their policies from there</span></span>
- <span data-ttu-id="2ded8-117">知道他們必須實施完整的 Microsoft 365 資訊保護堆疊，所以想要花更長的字詞，系統方式</span><span class="sxs-lookup"><span data-stu-id="2ded8-117">knowing that they need to implement the full Microsoft 365 Information Protection stack and so intend to take a longer term, methodical approach</span></span>

<span data-ttu-id="2ded8-118">以下是一些客戶如何使用 dlp 的範例，以及您從何處開始，Microsoft 365 DLP 都有足夠的彈性，可容納各種類型的資訊保護 journeys，從開始到完全意識的資料遺失防護策略。</span><span class="sxs-lookup"><span data-stu-id="2ded8-118">These are just some examples of how customers can approach DLP and it doesn't matter where you start from, Microsoft 365 DLP is flexible enough to accommodate various types of information protection journeys from start to a fully realized data loss prevention strategy.</span></span> 

## <a name="overview-of-planning-process"></a><span data-ttu-id="2ded8-119">規劃程式的概覽</span><span class="sxs-lookup"><span data-stu-id="2ded8-119">Overview of planning process</span></span>

<span data-ttu-id="2ded8-120">[深入瞭解資料遺失防護](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)引進了[DLP 規劃](dlp-learn-about-dlp.md#plan-for-dlp)程式的三個不同方面。</span><span class="sxs-lookup"><span data-stu-id="2ded8-120">The [Learn about data loss prevention](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) introduces the three different aspect of the [DLP planning process](dlp-learn-about-dlp.md#plan-for-dlp).</span></span> <span data-ttu-id="2ded8-121">我們將深入瞭解所有 DLP 計畫共有的元素。</span><span class="sxs-lookup"><span data-stu-id="2ded8-121">We'll go into more detail here on the elements that are common to all DLP plans.</span></span>

### <a name="identify-stakeholders"></a><span data-ttu-id="2ded8-122">識別專案關係人</span><span class="sxs-lookup"><span data-stu-id="2ded8-122">Identify stakeholders</span></span>

<span data-ttu-id="2ded8-123">實施時，DLP 原則可以套用到組織的大型部分。</span><span class="sxs-lookup"><span data-stu-id="2ded8-123">When implemented, DLP policies can be applied across large portions of your organization.</span></span> <span data-ttu-id="2ded8-124">它無法自行開發各種各樣的計畫，也不會產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="2ded8-124">IT can't develop a broad ranging plan on their own without negative consequences.</span></span> <span data-ttu-id="2ded8-125">您必須識別可以進行下列作業的利益關係人：</span><span class="sxs-lookup"><span data-stu-id="2ded8-125">You need to identify the stakeholders who can:</span></span>

- <span data-ttu-id="2ded8-126">描述您的組織受制于的規章、法律和工業標準</span><span class="sxs-lookup"><span data-stu-id="2ded8-126">describe the regulations, laws and industry standards your organization is subject to</span></span>
- <span data-ttu-id="2ded8-127">要保護的敏感專案類別</span><span class="sxs-lookup"><span data-stu-id="2ded8-127">the categories of sensitive items to be protected</span></span>
- <span data-ttu-id="2ded8-128">在其中使用的商務程式</span><span class="sxs-lookup"><span data-stu-id="2ded8-128">the business processes they are used in</span></span>
- <span data-ttu-id="2ded8-129">應該限制的危險行為</span><span class="sxs-lookup"><span data-stu-id="2ded8-129">the risky behavior that should be limited</span></span>
- <span data-ttu-id="2ded8-130">根據相關專案和風險的敏感度，以優先處理應該先保護的資料</span><span class="sxs-lookup"><span data-stu-id="2ded8-130">prioritize which data should be protected first based on the sensitivity of the items and risk involved</span></span>
- <span data-ttu-id="2ded8-131">概述 DLP 原則比對事件複查和修正程式</span><span class="sxs-lookup"><span data-stu-id="2ded8-131">outline the DLP policy match event review and remediation process</span></span> 
 
<span data-ttu-id="2ded8-132">一般來說，這些需求通常是85% 的規章和合規性保護，以及15% 的智慧財產權防護。</span><span class="sxs-lookup"><span data-stu-id="2ded8-132">In general these needs tend to be 85% regulatory and compliance protection, and 15% intellectual property protection.</span></span> <span data-ttu-id="2ded8-133">以下是有關在規劃程式中包含之角色的一些建議：</span><span class="sxs-lookup"><span data-stu-id="2ded8-133">Here are some suggestions on roles to include in your planning process:</span></span>

- <span data-ttu-id="2ded8-134">規範和合規性監察官</span><span class="sxs-lookup"><span data-stu-id="2ded8-134">Regulatory and compliance officers</span></span>
- <span data-ttu-id="2ded8-135">主要風險監察官</span><span class="sxs-lookup"><span data-stu-id="2ded8-135">Chief risk officer</span></span>
- <span data-ttu-id="2ded8-136">法律監察官</span><span class="sxs-lookup"><span data-stu-id="2ded8-136">Legal officers</span></span>
- <span data-ttu-id="2ded8-137">安全性與合規性監察官</span><span class="sxs-lookup"><span data-stu-id="2ded8-137">Security and compliance officers</span></span>
- <span data-ttu-id="2ded8-138">資料項目的企業擁有者</span><span class="sxs-lookup"><span data-stu-id="2ded8-138">Business owners for the data items</span></span>
- <span data-ttu-id="2ded8-139">商務使用者</span><span class="sxs-lookup"><span data-stu-id="2ded8-139">Business users</span></span>
- <span data-ttu-id="2ded8-140">IT</span><span class="sxs-lookup"><span data-stu-id="2ded8-140">IT</span></span>

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a><span data-ttu-id="2ded8-141">描述要保護的敏感資訊類別</span><span class="sxs-lookup"><span data-stu-id="2ded8-141">Describe the categories of sensitive information to protect</span></span>

<span data-ttu-id="2ded8-142">然後，干係人會描述要保護的敏感資訊類別，以及其所用的商務程式。</span><span class="sxs-lookup"><span data-stu-id="2ded8-142">The stakeholders then describe the categories of sensitive information to be protected and the business process that they're used in.</span></span> <span data-ttu-id="2ded8-143">例如，Microsoft 365 DLP 會定義下列類別：</span><span class="sxs-lookup"><span data-stu-id="2ded8-143">For example, Microsoft 365 DLP defines these categories:</span></span>

- <span data-ttu-id="2ded8-144">金融業</span><span class="sxs-lookup"><span data-stu-id="2ded8-144">Financial</span></span> 
- <span data-ttu-id="2ded8-145">醫療和健康情況資訊</span><span class="sxs-lookup"><span data-stu-id="2ded8-145">Medical and health information</span></span>
- <span data-ttu-id="2ded8-146">隱私權</span><span class="sxs-lookup"><span data-stu-id="2ded8-146">Privacy</span></span>
- <span data-ttu-id="2ded8-147">自訂</span><span class="sxs-lookup"><span data-stu-id="2ded8-147">Custom</span></span>

<span data-ttu-id="2ded8-148">因為「我們是資料處理器，所以相關者可能會識別敏感資訊，因此我們必須對資料主體資訊和財務資訊執行隱私權保護」。</span><span class="sxs-lookup"><span data-stu-id="2ded8-148">The stakeholders might identify the sensitive information as "We are a data processor, so we have to implement privacy protections on data subject information and financial information".</span></span>

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a><span data-ttu-id="2ded8-149">設定目標與策略</span><span class="sxs-lookup"><span data-stu-id="2ded8-149">Set goals and strategy</span></span>

<span data-ttu-id="2ded8-150">一旦您識別出您的利益關係人，而且知道哪些機密資訊需要保護，以及其使用的位置，專案關係人就能設定其保護目標，而且可以制定實施計畫。</span><span class="sxs-lookup"><span data-stu-id="2ded8-150">Once you have identified your stakeholders and you know which sensitive information needs protection and where it's used, the stakeholders can set their protection goals and IT can develop an implementation plan.</span></span> 


 <!--
### Discovery
 for the locations (DLP workloads) of these types of items.  (mapping DLP locations and data at rest, data in transit, data in use)

### IT can start coding test policies
start small and always in test mode. Note that DLP policies can feed into insider risk.

### Business process owners help with tuning
 false positive/false negative results and fitting DLP into their business processes.

-->

### <a name="set-implementation-plan"></a><span data-ttu-id="2ded8-151">設定實施方案</span><span class="sxs-lookup"><span data-stu-id="2ded8-151">Set implementation plan</span></span>

<span data-ttu-id="2ded8-152">您的實施計畫應包括：</span><span class="sxs-lookup"><span data-stu-id="2ded8-152">Your implementation plan should include:</span></span>

- <span data-ttu-id="2ded8-153">對應您的起始狀態和期望的結束狀態，以及從一到另一個中取得的步驟。</span><span class="sxs-lookup"><span data-stu-id="2ded8-153">Mapping out your starting state and desired end state and the steps to get from one to the other</span></span>
- <span data-ttu-id="2ded8-154">如何處理機密專案的探索</span><span class="sxs-lookup"><span data-stu-id="2ded8-154">how you will address discovery of sensitive items</span></span>
- <span data-ttu-id="2ded8-155">原則規劃，以及其所要執行的順序</span><span class="sxs-lookup"><span data-stu-id="2ded8-155">policy planning and the order that they will be implemented</span></span>
- <span data-ttu-id="2ded8-156">您將如何處理任何必要條件</span><span class="sxs-lookup"><span data-stu-id="2ded8-156">how you will address any prerequisites</span></span>
- <span data-ttu-id="2ded8-157">在移動至強制執行之前，先規劃如何測試原則</span><span class="sxs-lookup"><span data-stu-id="2ded8-157">planning on how policies will first be tested before moving to enforcement</span></span>
- <span data-ttu-id="2ded8-158">如何訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="2ded8-158">how you will train your end users</span></span>
- <span data-ttu-id="2ded8-159">測試及調整原則的方式</span><span class="sxs-lookup"><span data-stu-id="2ded8-159">how you will test and tune your policies</span></span>
- <span data-ttu-id="2ded8-160">如何根據變更法規、法律、行業標準或智慧財產權保護和業務需求，檢查和更新資料遺失防護策略</span><span class="sxs-lookup"><span data-stu-id="2ded8-160">how you will review and update your data loss prevention strategy based on changing regulatory, legal, industry standard or intellectual property protection and business needs</span></span>

#### <a name="map-out-path-from-start-to-desired-end-state"></a><span data-ttu-id="2ded8-161">從開始到想要的結束狀態對應出路徑</span><span class="sxs-lookup"><span data-stu-id="2ded8-161">Map out path from start to desired end state</span></span>

<span data-ttu-id="2ded8-162">記錄您的組織從其開始狀態到所需結束狀態的方式，對與您的專案關係人進行通訊和設定專案範圍而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="2ded8-162">Documenting how your organization is going to get from its starting state to the desired end state is essential to communicating with your stakeholders and setting the project scope.</span></span> <span data-ttu-id="2ded8-163">以下是一組一般用於部署 DLP 的步驟。</span><span class="sxs-lookup"><span data-stu-id="2ded8-163">Here are a set of steps that are commonly used to deploy DLP.</span></span> <span data-ttu-id="2ded8-164">您將需要更詳細的資訊，但您可以使用此程式來圖文 DLP 採用路徑。</span><span class="sxs-lookup"><span data-stu-id="2ded8-164">You'll want more detail than this, but you can use this to frame your DLP adoption path.</span></span>

![顯示部署 DLP 之常見順序的圖形](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a><span data-ttu-id="2ded8-166">敏感專案探索</span><span class="sxs-lookup"><span data-stu-id="2ded8-166">Sensitive item discovery</span></span>

<span data-ttu-id="2ded8-167">有多種方式可以發現個別機密專案的所在位置和位置。</span><span class="sxs-lookup"><span data-stu-id="2ded8-167">There are multiple ways to discover what individual sensitive items are and where they are located.</span></span> <span data-ttu-id="2ded8-168">您可能已經部署了靈敏度標籤，或已決定將非常廣泛的 DLP 原則部署到只探索及審核專案的所有位置。</span><span class="sxs-lookup"><span data-stu-id="2ded8-168">You may have sensitivity labels already deployed or you may have decided to deploy a very broad DLP policy to all locations that only discovers and audits items.</span></span> <span data-ttu-id="2ded8-169">若要深入瞭解，請參閱 [瞭解您的資料](information-protection.md#know-your-data)。</span><span class="sxs-lookup"><span data-stu-id="2ded8-169">To learn more, see [Know your data](information-protection.md#know-your-data).</span></span>

#### <a name="policy-planning"></a><span data-ttu-id="2ded8-170">原則規劃</span><span class="sxs-lookup"><span data-stu-id="2ded8-170">Policy planning</span></span>

<span data-ttu-id="2ded8-171">當您開始 DLP 採用時，您可以使用這些問題，將您的原則設計與實施工作重點放在一起。</span><span class="sxs-lookup"><span data-stu-id="2ded8-171">As you begin your DLP adoption you can use these questions to focus your policy design and implementation efforts.</span></span>

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a><span data-ttu-id="2ded8-172">您的組織必須遵守哪些法律、法規和行業標準？</span><span class="sxs-lookup"><span data-stu-id="2ded8-172">What laws, regulations and industry standards must your organization comply with?</span></span>

<span data-ttu-id="2ded8-173">由於許多組織會隨著法規遵從性目標進入 DLP，所以回答此問題是規劃 DLP 實現的自然起點。</span><span class="sxs-lookup"><span data-stu-id="2ded8-173">Because many organizations come to DLP with the goal of regulatory compliance, answering this question is a natural starting place for planning your DLP implementation.</span></span> <span data-ttu-id="2ded8-174">不過，隨著 IT 的實施，您可能不會進行解答。</span><span class="sxs-lookup"><span data-stu-id="2ded8-174">But, as the IT implementer, you're probably not positioned to answer it.</span></span> <span data-ttu-id="2ded8-175">您必須由法律小組和商務主管人員解答。</span><span class="sxs-lookup"><span data-stu-id="2ded8-175">It needs to be answered by your legal team and business executives.</span></span> 
 
<span data-ttu-id="2ded8-176">**範例** 您的組織受制于英國</span><span class="sxs-lookup"><span data-stu-id="2ded8-176">**Example** Your organization is subject to U.K.</span></span> <span data-ttu-id="2ded8-177">金融規章。</span><span class="sxs-lookup"><span data-stu-id="2ded8-177">financial regulations.</span></span>


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a><span data-ttu-id="2ded8-178">您的組織必須保護哪些敏感專案，使其不會洩漏？</span><span class="sxs-lookup"><span data-stu-id="2ded8-178">What sensitive items does your organization have that must be protected from leakage?</span></span>

<span data-ttu-id="2ded8-179">當您的組織知道其在法規遵從性需求方面的含義時，您將會瞭解哪些敏感專案需要保護以避免洩漏，以及您要如何設定原則實施的優先順序，以加以保護。</span><span class="sxs-lookup"><span data-stu-id="2ded8-179">Once your organization knows where it stands in terms of regulatory compliance needs, you'll have some idea of what sensitive items need to be protected from leakage and how you want to prioritize policy implementation to protect them.</span></span> <span data-ttu-id="2ded8-180">這可協助您選擇最適當的 DLP 原則範本。</span><span class="sxs-lookup"><span data-stu-id="2ded8-180">This will help you choose the most appropriate DLP policy templates.</span></span> <span data-ttu-id="2ded8-181">Microsoft 365 隨附的是針對財務、醫療和健康情況、隱私權的預先設定 DLP 範本，您可以使用自訂範本自行建立。</span><span class="sxs-lookup"><span data-stu-id="2ded8-181">Microsoft 365 comes with pre-configured DLP templates for Financial, Medical and health, Privacy, and you can build your own using the Custom template.</span></span> <span data-ttu-id="2ded8-182">在您設計及建立實際的 DLP 原則時，知道問題的答案也會協助您選擇正確的 [敏感資訊類型](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)。</span><span class="sxs-lookup"><span data-stu-id="2ded8-182">As you design and create your actual DLP policies, knowing the answer to this question will also help you choose the right [sensitive information type](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types).</span></span>

<span data-ttu-id="2ded8-183">**範例** 若要快速開始，請選取 `U.K. Financial Data` 原則範本，包含 `Credit Card Number` 、 `EU Debit Card Number` 和 `SWIFT Code` 敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2ded8-183">**Example** To get started quickly, you pick the `U.K. Financial Data` policy template which includes the `Credit Card Number`, `EU Debit Card Number`, and `SWIFT Code` sensitive information types.</span></span> 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a><span data-ttu-id="2ded8-184">機密專案及其相關的商務程式在哪裡？</span><span class="sxs-lookup"><span data-stu-id="2ded8-184">Where are the sensitive items and what business processes are they involved in?</span></span>

<span data-ttu-id="2ded8-185">包含組織機密資訊的專案每天都會在經營過程中使用。</span><span class="sxs-lookup"><span data-stu-id="2ded8-185">The items that contain your organizations sensitive information are used every day in the course of doing business.</span></span> <span data-ttu-id="2ded8-186">您必須知道敏感資訊的實例可能發生的位置，以及其所使用的商務程式。</span><span class="sxs-lookup"><span data-stu-id="2ded8-186">You need to know where instances of that sensitive information may occur and what business processes they are used in.</span></span> <span data-ttu-id="2ded8-187">這可協助您選擇要將 DLP 原則套用至哪個適當位置。</span><span class="sxs-lookup"><span data-stu-id="2ded8-187">This will help you choose the right locations to apply your DLP policies to.</span></span> <span data-ttu-id="2ded8-188">Microsoft 365DLP 原則會套用至下列位置：</span><span class="sxs-lookup"><span data-stu-id="2ded8-188">Microsoft 365 DLP policies are applied to locations:</span></span>

- <span data-ttu-id="2ded8-189">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="2ded8-189">Exchange email</span></span>
- <span data-ttu-id="2ded8-190">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="2ded8-190">SharePoint sites</span></span>
- <span data-ttu-id="2ded8-191">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="2ded8-191">OneDrive accounts</span></span>
- <span data-ttu-id="2ded8-192">Teams 聊天和頻道訊息</span><span class="sxs-lookup"><span data-stu-id="2ded8-192">Teams chat and channel messages</span></span>
- <span data-ttu-id="2ded8-193">Windows 10設備</span><span class="sxs-lookup"><span data-stu-id="2ded8-193">Windows 10 Devices</span></span>
- <span data-ttu-id="2ded8-194">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="2ded8-194">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2ded8-195">內部部署存放庫</span><span class="sxs-lookup"><span data-stu-id="2ded8-195">On-premises repositories</span></span>

<span data-ttu-id="2ded8-196">**範例** 您組織的內部稽核員正在追蹤一組信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="2ded8-196">**Example** Your organizations' internal auditors are tracking a set of credit card numbers.</span></span> <span data-ttu-id="2ded8-197">它們會在安全的 SharePoint 網站中保存它們的試算表。</span><span class="sxs-lookup"><span data-stu-id="2ded8-197">They keep a spreadsheet of them in a secure SharePoint site.</span></span> <span data-ttu-id="2ded8-198">有些員工會製作副本，並將其儲存到與其 Windows 10 裝置同步處理商務用 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="2ded8-198">Several of the employees make copies and save them to their work OneDrive for Business site which is synced to their Windows 10 device.</span></span> <span data-ttu-id="2ded8-199">其中一個會在電子郵件中貼上其中的14個清單，並嘗試將其傳送至外部審計員進行審閱。</span><span class="sxs-lookup"><span data-stu-id="2ded8-199">One of them pastes a list of 14 of them in an email and tries to send it to the outside auditors for review.</span></span> <span data-ttu-id="2ded8-200">您想要將原則套用至安全 SharePoint 網站，所有內部稽核員商務用 OneDrive 帳戶、其 Windows 10 裝置及 Exchange 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2ded8-200">You'd want to apply the policy to the secure SharePoint site, all the internal auditors OneDrive for Business accounts, their Windows 10 devices and Exchange email.</span></span>

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a><span data-ttu-id="2ded8-201">您的組織的洩漏容限程度為何？</span><span class="sxs-lookup"><span data-stu-id="2ded8-201">What is your organizations tolerance for leakage?</span></span>

<span data-ttu-id="2ded8-202">您組織中的不同群組可能會有不同的觀點，也就是可接受的敏感專案洩漏層級和不是什麼。</span><span class="sxs-lookup"><span data-stu-id="2ded8-202">Different groups in your organization may have different views on what's an acceptable level of sensitive item leakage and what's not.</span></span> <span data-ttu-id="2ded8-203">取得零次洩漏的完美，可能會導致公司成本過高。</span><span class="sxs-lookup"><span data-stu-id="2ded8-203">Achieving the perfection of zero leakage may come at too high a cost to the business.</span></span>

<span data-ttu-id="2ded8-204">**範例** 組織的安全性群組和法律小組都會感覺，您應該不會與組織外的任何人共用信用卡號碼，而且堅持使用零的洩漏。</span><span class="sxs-lookup"><span data-stu-id="2ded8-204">**Example** Your organizations' security group, along with the legal team both feel that there should be no sharing of credit card numbers with anyone outside the org and insist on zero leakage.</span></span> <span data-ttu-id="2ded8-205">不過，當您定期複查信用卡號碼活動時，內部稽核員必須與協力廠商審計員共用某些信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="2ded8-205">But, as part of regular review of credit card number activity, the internal auditors must share some credit card numbers with third party auditors.</span></span> <span data-ttu-id="2ded8-206">如果您的 DLP 原則禁止所有共用該組織外部的信用卡號碼，則可能會有重要的業務流程中斷，增加成本以降低內部稽核員完成其追蹤的中斷順序。</span><span class="sxs-lookup"><span data-stu-id="2ded8-206">If your DLP policy prohibits all sharing of credit card numbers outside the org, there will be a significant business process disruption and added cost to mitigate the disruption in order for the internal auditors to complete their tracking.</span></span> <span data-ttu-id="2ded8-207">這種額外的成本對執行能力的領導作用不可接受。</span><span class="sxs-lookup"><span data-stu-id="2ded8-207">This extra cost is unacceptable to the executive leadership.</span></span> <span data-ttu-id="2ded8-208">若要解決此問題，您必須要有內部交談才能決定可接受的洩漏層級。</span><span class="sxs-lookup"><span data-stu-id="2ded8-208">To resolve this, there needs to be an internal conversation to decide an acceptable level of leakage.</span></span> <span data-ttu-id="2ded8-209">一旦決定原則，便可為特定個人提供例外狀況，以共用資訊，或以「僅供審核」模式套用。</span><span class="sxs-lookup"><span data-stu-id="2ded8-209">Once that is decided the policy can provide exceptions for certain individuals to share the information or it can be applied in audit only mode.</span></span>

#### <a name="planning-for-prerequisites"></a><span data-ttu-id="2ded8-210">規劃必要條件</span><span class="sxs-lookup"><span data-stu-id="2ded8-210">Planning for prerequisites</span></span>

<span data-ttu-id="2ded8-211">在您可以監視某些 DLP 位置之前，必須符合必要的必要條件。</span><span class="sxs-lookup"><span data-stu-id="2ded8-211">Before you can monitor some DLP locations, there are prerequisites that must be met.</span></span> <span data-ttu-id="2ded8-212">**開始之前**，請參閱下列各節：</span><span class="sxs-lookup"><span data-stu-id="2ded8-212">See the **Before you begin** sections of:</span></span>

- [<span data-ttu-id="2ded8-213">開始使用資料外洩防護內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="2ded8-213">Get started with the data loss prevention on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [<span data-ttu-id="2ded8-214">開始使用端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="2ded8-214">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md#before-you-begin)
- [<span data-ttu-id="2ded8-215">開始使用 Microsoft 規範擴充 (預覽) </span><span class="sxs-lookup"><span data-stu-id="2ded8-215">Get started with the Microsoft compliance extension (preview)</span></span>](dlp-chrome-get-started.md#before-you-begin)
- [<span data-ttu-id="2ded8-216">使用非 Microsoft cloud app 的資料遺失防護原則 (預覽) </span><span class="sxs-lookup"><span data-stu-id="2ded8-216">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a><span data-ttu-id="2ded8-217">原則部署</span><span class="sxs-lookup"><span data-stu-id="2ded8-217">Policy deployment</span></span>

<span data-ttu-id="2ded8-218">建立 DLP 原則時，您應考慮逐漸推出這些原則，以便在完全強制執行之前評估其影響及測試其效果。</span><span class="sxs-lookup"><span data-stu-id="2ded8-218">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="2ded8-219">例如，您不想讓新的 DLP 原則無意間封鎖存取數千份檔，或中斷現有的商務程式。</span><span class="sxs-lookup"><span data-stu-id="2ded8-219">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents or to break an existing business process.</span></span>
  
<span data-ttu-id="2ded8-220">如果您正在建立的 DLP 原則可能有重大影響，建議依照下列順序進行：</span><span class="sxs-lookup"><span data-stu-id="2ded8-220">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="2ded8-221">**以測試模式啟動但不顯示原則提示**，然後使用 DLP 報告和任何事件報告來評估影響。</span><span class="sxs-lookup"><span data-stu-id="2ded8-221">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="2ded8-222">您可以使用 DLP 報告來檢視原則相符項目的號碼、位置、類型和嚴重性。</span><span class="sxs-lookup"><span data-stu-id="2ded8-222">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="2ded8-223">根據結果，您可以視需要微調原則。</span><span class="sxs-lookup"><span data-stu-id="2ded8-223">Based on the results, you can fine tune the policies as needed.</span></span> <span data-ttu-id="2ded8-224">在測試模式中，DLP 原則不會影響您的組織中工作人員的生產力。</span><span class="sxs-lookup"><span data-stu-id="2ded8-224">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> <span data-ttu-id="2ded8-225">此外，您也可以使用此階段測試工作流程，以進行 DLP 事件評審及問題修復。</span><span class="sxs-lookup"><span data-stu-id="2ded8-225">Also, use this stage to test out your workflow for DLP event review and issue remediation.</span></span>
    
2. <span data-ttu-id="2ded8-226">**移至具有通知和原則提示的測試模式**，讓您可以開始向使用者講授您的規範原則，並為將要套用的原則做好準備。</span><span class="sxs-lookup"><span data-stu-id="2ded8-226">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the policies that are going to be applied.</span></span> <span data-ttu-id="2ded8-227">其可提供組織原則頁面的連結，以提供原則提示中原則的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2ded8-227">Its useful to have a link to an organization policy page that provides additional details about the policy in the policy tip.</span></span> <span data-ttu-id="2ded8-228">在此階段中，您也可以要求使用者報告誤報，以便進一步精煉原則。</span><span class="sxs-lookup"><span data-stu-id="2ded8-228">At this stage, you can also ask users to report false positives so that you can further refine the policies.</span></span> <span data-ttu-id="2ded8-229">一旦您確信原則應用程式的結果符合他們的利益關係人的觀點，請移至此階段。</span><span class="sxs-lookup"><span data-stu-id="2ded8-229">Move to this stage once you have confidence that the results of policy application match what they stakeholders had in mind.</span></span> 
    
3. <span data-ttu-id="2ded8-230">**開始完整強制執行原則**，以便套用規則中的動作，並保護內容。</span><span class="sxs-lookup"><span data-stu-id="2ded8-230">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="2ded8-231">繼續監視 DLP 報告以及任何事件報告或通知，確保得到您想要的結果。</span><span class="sxs-lookup"><span data-stu-id="2ded8-231">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 

    ![使用測試模式和開啟原則的選項](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    <span data-ttu-id="2ded8-233">您可以隨時關閉 DLP 原則，關閉會影響原則中的所有規則。</span><span class="sxs-lookup"><span data-stu-id="2ded8-233">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="2ded8-234">不過，也可以藉由在規則編輯器中切換每個規則的狀態來個別關閉規則。</span><span class="sxs-lookup"><span data-stu-id="2ded8-234">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>

    ![在原則中關閉規則的選項](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    <span data-ttu-id="2ded8-236">您也可以變更原則中多個規則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="2ded8-236">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="2ded8-237">若要這樣做，請開啟原則進行編輯。</span><span class="sxs-lookup"><span data-stu-id="2ded8-237">To do that, open a policy for editing.</span></span> <span data-ttu-id="2ded8-238">在規則列中，選擇省略符號 (**...**)，然後選擇一個選項，例如 **[下移]** 或 **[移至最後]**。</span><span class="sxs-lookup"><span data-stu-id="2ded8-238">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

    ![設定規則優先順序](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a><span data-ttu-id="2ded8-240">使用者訓練</span><span class="sxs-lookup"><span data-stu-id="2ded8-240">End user training</span></span>

<span data-ttu-id="2ded8-241">當您觸發 DLP 原則時，您可以設定您的原則，以 [傳送電子郵件通知，並向系統管理員和使用者顯示 DLP 原則的原則秘訣](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) 。</span><span class="sxs-lookup"><span data-stu-id="2ded8-241">When a DLP policy is triggered, you can configure your policies to [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) to admins and end users.</span></span> <span data-ttu-id="2ded8-242">雖然您的原則仍在測試模式中，而且在設定為強制執行封鎖動作之前，原則提示是有效的方式，可以進一步瞭解敏感專案的危險行為，並訓練使用者避免未來的行為。</span><span class="sxs-lookup"><span data-stu-id="2ded8-242">While your policies are still in test mode and before they are set to enforce a blocking action, policy tips are useful ways to raise awareness of risky behaviors on sensitive items and train users to avoid those behaviors in the future.</span></span>  

#### <a name="review-dlp-requirements-and-update-strategy"></a><span data-ttu-id="2ded8-243">檢查 DLP 需求和更新策略</span><span class="sxs-lookup"><span data-stu-id="2ded8-243">Review DLP requirements and update strategy</span></span>

<span data-ttu-id="2ded8-244">您的組織可能會隨著時間而變更的規章、法律和行業標準，DLP 的商務目標也會隨之變更。</span><span class="sxs-lookup"><span data-stu-id="2ded8-244">The regulations, laws and industry standards that your organization is subject to will change over time and your business goals for DLP will too.</span></span> <span data-ttu-id="2ded8-245">請務必定期查看所有這些區域，使您的組織維持在法規遵從性之外，而且 DLP 實施仍可滿足您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="2ded8-245">Be sure to include regular reviews of all these areas so that your organization stays in compliance and your DLP implementation continues to meet your business needs.</span></span>

## <a name="approaches-to-deployment"></a><span data-ttu-id="2ded8-246">部署方法</span><span class="sxs-lookup"><span data-stu-id="2ded8-246">Approaches to deployment</span></span>

|<span data-ttu-id="2ded8-247">客戶業務需求說明</span><span class="sxs-lookup"><span data-stu-id="2ded8-247">Customer business needs description</span></span>  | <span data-ttu-id="2ded8-248">方法</span><span class="sxs-lookup"><span data-stu-id="2ded8-248">approach</span></span>  |
|---------|---------|
|<span data-ttu-id="2ded8-249">**Contoso Bank** 位於高度管制的行業，在許多不同的位置有許多不同類型的敏感專案。</span><span class="sxs-lookup"><span data-stu-id="2ded8-249">**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations.</span></span> </br> <span data-ttu-id="2ded8-250">-瞭解哪些類型的敏感資訊是最重要的。</span><span class="sxs-lookup"><span data-stu-id="2ded8-250">- knows which types of sensitive information are top priority.</span></span> </br> <span data-ttu-id="2ded8-251">-當原則向外展開時，必須將業務中斷降至最低。</span><span class="sxs-lookup"><span data-stu-id="2ded8-251">- must minimize business disruption as policies are rolled out.</span></span> </br> <span data-ttu-id="2ded8-252">-有 IT 資源，而且可以聘用專家協助規劃、設計部署</span><span class="sxs-lookup"><span data-stu-id="2ded8-252">-  has IT resources and can hire experts to help plan, design deploy</span></span> </br> <span data-ttu-id="2ded8-253">-與 Microsoft 有 premier 支援合同</span><span class="sxs-lookup"><span data-stu-id="2ded8-253">- has a premier support contract with Microsoft</span></span>| <span data-ttu-id="2ded8-254">-請花些時間瞭解他們必須遵守哪些規章，以及這些法規的遵守方式。</span><span class="sxs-lookup"><span data-stu-id="2ded8-254">- Take the time to understand what regulations they must comply with and how they are going to comply.</span></span> </br> <span data-ttu-id="2ded8-255">-請花時間深入瞭解 Microsoft 365 資訊保護堆疊的整體價值</span><span class="sxs-lookup"><span data-stu-id="2ded8-255">-Take the time to understand the better together value of the Microsoft 365 Information Protection stack</span></span> </br> <span data-ttu-id="2ded8-256">-針對已設定優先順序的專案，開發敏感度標籤配置，並套用</span><span class="sxs-lookup"><span data-stu-id="2ded8-256">- Develop sensitivity labelling scheme for prioritized items and apply</span></span> </br> <span data-ttu-id="2ded8-257">-包含業務程式擁有者</span><span class="sxs-lookup"><span data-stu-id="2ded8-257">- Involve business process owners</span></span> </br><span data-ttu-id="2ded8-258">-設計/程式碼原則，在測試模式中部署，以訓練使用者</span><span class="sxs-lookup"><span data-stu-id="2ded8-258">- Design/code policies, deploy in test mode, train users</span></span> </br><span data-ttu-id="2ded8-259">-重複</span><span class="sxs-lookup"><span data-stu-id="2ded8-259">- repeat</span></span>|
|<span data-ttu-id="2ded8-260">**TailSpin 玩具** 不知道其所在的位置或位置，且幾乎不會有任何資源深度。</span><span class="sxs-lookup"><span data-stu-id="2ded8-260">**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth.</span></span> <span data-ttu-id="2ded8-261">它們會大量使用 Teams、ODB 及 Exchange。</span><span class="sxs-lookup"><span data-stu-id="2ded8-261">They use Teams, ODB and Exchange extensively.</span></span>     |<span data-ttu-id="2ded8-262">-從優先位置的簡單原則開始。</span><span class="sxs-lookup"><span data-stu-id="2ded8-262">- Start with simple policies on the prioritized locations.</span></span> </br><span data-ttu-id="2ded8-263">-監視識別的專案</span><span class="sxs-lookup"><span data-stu-id="2ded8-263">- Monitor what gets identified</span></span> </br><span data-ttu-id="2ded8-264">-據此套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="2ded8-264">- Apply sensitivity labels accordingly</span></span> </br><span data-ttu-id="2ded8-265">-調整原則，訓練使用者</span><span class="sxs-lookup"><span data-stu-id="2ded8-265">- Refine policies, train users</span></span>       |
|<span data-ttu-id="2ded8-266">**Fabrikam** 是一小的啟動，想要保護其智慧財產權，而且必須快速移動。</span><span class="sxs-lookup"><span data-stu-id="2ded8-266">**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly.</span></span> <span data-ttu-id="2ded8-267">他們願意專用一些資源，但無法承受聘用在專家之外的人員。</span><span class="sxs-lookup"><span data-stu-id="2ded8-267">They are willing to dedicate some resources, but can't afford hiring outside experts.</span></span> </br><span data-ttu-id="2ded8-268">-敏感專案全都位於商務用 Microsoft 365 OneDdrive 中/SharePoint</span><span class="sxs-lookup"><span data-stu-id="2ded8-268">- Sensitive items are all in Microsoft 365 OneDdrive for Business/SharePoint</span></span> </br><span data-ttu-id="2ded8-269">-商務用 OneDrive 和 SharePoint 的採用速度緩慢、員工/陰影使用 DropBox 和 Google 磁片磁碟機來共用/儲存專案</span><span class="sxs-lookup"><span data-stu-id="2ded8-269">- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items</span></span> </br><span data-ttu-id="2ded8-270">-員工在資料保護訓練科目上的工作速度</span><span class="sxs-lookup"><span data-stu-id="2ded8-270">- Employees value speed of work over data protection discipline</span></span> </br><span data-ttu-id="2ded8-271">-客戶 splurged 並購買所有18位員工新 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="2ded8-271">- Customer splurged and bought all 18 employees new Windows 10 devices</span></span>     |<span data-ttu-id="2ded8-272">-利用 Teams 中的預設 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="2ded8-272">- Take advantage of the default DLP policy in Teams</span></span> </br><span data-ttu-id="2ded8-273">-使用 SharePoint 專案的預設限制設定</span><span class="sxs-lookup"><span data-stu-id="2ded8-273">- Use restricted by default setting for SharePoint items</span></span> </br><span data-ttu-id="2ded8-274">-部署防止外部共用的原則</span><span class="sxs-lookup"><span data-stu-id="2ded8-274">- Deploy policies that prevent external sharing</span></span> </br><span data-ttu-id="2ded8-275">-部署設定優先順序的位置的原則</span><span class="sxs-lookup"><span data-stu-id="2ded8-275">- Deploy policies to prioritized locations</span></span> </br><span data-ttu-id="2ded8-276">-部署 Windows 10 裝置的原則</span><span class="sxs-lookup"><span data-stu-id="2ded8-276">- Deploy policies to Windows 10 devices</span></span> </br><span data-ttu-id="2ded8-277">-封鎖上載至非商務用 OneDrive 雲端儲存</span><span class="sxs-lookup"><span data-stu-id="2ded8-277">- Block uploads to non OneDrive for Business cloud storage</span></span>      |

<!--

## Planning for workloads

### Exchange

### SharePoint

### OneDrive for Business

### Teams

### Windows 10 Devices

### Microsoft Cloud App Security (MCAS)

### On-premises Scanner
-->

## <a name="see-also"></a><span data-ttu-id="2ded8-278">請參閱</span><span class="sxs-lookup"><span data-stu-id="2ded8-278">See also</span></span>
- [<span data-ttu-id="2ded8-279">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="2ded8-279">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
