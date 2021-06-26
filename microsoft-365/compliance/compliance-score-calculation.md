---
title: 合規性分數計算
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解 Microsoft 合規性管理員如何根據採取的措施來計算個人化分數，以解決風險並改善您的相容性狀況。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4e1e3f4b90b0a5e83a1e068cd30f76b3a8c7bb22
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149163"
---
# <a name="compliance-score-calculation"></a><span data-ttu-id="02da4-103">合規性分數計算</span><span class="sxs-lookup"><span data-stu-id="02da4-103">Compliance score calculation</span></span>

<span data-ttu-id="02da4-104">**本文內容：** 瞭解合規性管理員如何計算組織的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="02da4-104">**In this article:** Learn how Compliance Manager calculates a compliance score for your organization.</span></span> <span data-ttu-id="02da4-105">本文說明如何 **轉譯您的分數**、 **資料保護基準評估** 包含的內容、 **連續監控**，以及 **如何管理和計分不同類型的動作**。</span><span class="sxs-lookup"><span data-stu-id="02da4-105">This article explains how to **interpret your score**, what the **Data Protection Baseline assessment** includes, **continuous monitoring**, and **how different types of actions are managed and scored**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02da4-106">您不應將 [合規性管理員] 提供的建議視為合規性的保證。</span><span class="sxs-lookup"><span data-stu-id="02da4-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="02da4-107">您可以根據法規環境評估和驗證客戶控制措施的效能。</span><span class="sxs-lookup"><span data-stu-id="02da4-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="02da4-108">這些服務須遵守 [線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。</span><span class="sxs-lookup"><span data-stu-id="02da4-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="02da4-109">另請參閱[Microsoft 365 授權指南以取得安全性和合規性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="02da4-109">See also [Microsoft 365 licensing guidance for security and compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="how-to-read-your-compliance-score"></a><span data-ttu-id="02da4-110">如何閱讀您的合規性分數</span><span class="sxs-lookup"><span data-stu-id="02da4-110">How to read your compliance score</span></span>

<span data-ttu-id="02da4-111">合規性管理員儀表板會顯示您的整體合規性分數。</span><span class="sxs-lookup"><span data-stu-id="02da4-111">The Compliance Manager dashboard displays your overall compliance score.</span></span> <span data-ttu-id="02da4-112">這個分數會度量您在完成控制項中建議的改進動作時的進度。</span><span class="sxs-lookup"><span data-stu-id="02da4-112">This score measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="02da4-113">您的分數可協助您瞭解目前的相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="02da4-113">Your score can help you understand your current compliance posture.</span></span> <span data-ttu-id="02da4-114">它也可協助您根據其可能降低風險的可能性來排定動作優先順序。</span><span class="sxs-lookup"><span data-stu-id="02da4-114">It can also help you prioritize actions based on their potential to reduce risk.</span></span>

<span data-ttu-id="02da4-115">分數值會指派給三個層級：</span><span class="sxs-lookup"><span data-stu-id="02da4-115">A score value is assigned at three levels:</span></span>

1. <span data-ttu-id="02da4-116">**改進動作分數**：每項動作對您的分數有不同的影響，取決於可能的風險</span><span class="sxs-lookup"><span data-stu-id="02da4-116">**Improvement action score**: each action has a different impact on your score depending on the potential risk involved</span></span>

2. <span data-ttu-id="02da4-117">**控制分數**：此分數是在控制項內完成改進動作所取得的點數總和。</span><span class="sxs-lookup"><span data-stu-id="02da4-117">**Control score**: this score is the sum of points earned by completing improvement actions within the control.</span></span> <span data-ttu-id="02da4-118">當控制項同時滿足下列兩個條件時，此總和會整體套用到整體合規性分數：</span><span class="sxs-lookup"><span data-stu-id="02da4-118">This sum is applied in its entirety to your overall compliance score when the control meets both of the following conditions:</span></span>
    - <span data-ttu-id="02da4-119">**實施狀態** 等於 [已 **實現** ] 或 [ **替代] 實施**，以及</span><span class="sxs-lookup"><span data-stu-id="02da4-119">**Implementation Status** equals **Implemented** or **Alternative Implementation**, and</span></span>
    - <span data-ttu-id="02da4-120">已 **通過\*\*\*\*測試結果** equals。</span><span class="sxs-lookup"><span data-stu-id="02da4-120">**Test Result** equals **Passed**.</span></span>

3. <span data-ttu-id="02da4-121">**評估分數**：此分數是控制項分數的總和。</span><span class="sxs-lookup"><span data-stu-id="02da4-121">**Assessment score**: this score is the sum of your control scores.</span></span> <span data-ttu-id="02da4-122">它是以動作分數計算。</span><span class="sxs-lookup"><span data-stu-id="02da4-122">It is calculated using action scores.</span></span> <span data-ttu-id="02da4-123">每個 Microsoft 動作和您組織所管理的每個改進動作都會計算一次，不論它在控制項中的參照頻率為何。</span><span class="sxs-lookup"><span data-stu-id="02da4-123">Each Microsoft action and each improvement action managed by your organization is counted once, regardless of how often it is referenced in a control.</span></span>

<span data-ttu-id="02da4-124">整體符合性分數是以動作分數計算，其中每個 Microsoft 動作都會計算一次，每個您管理的技術動作都會計算一次，而您管理的每個非技術動作都會針對每個群組計算一次。</span><span class="sxs-lookup"><span data-stu-id="02da4-124">The overall compliance score is calculated using action scores, where each Microsoft action is counted once, each technical action you manage is counted once, and each non-technical action you manage is counted once per group.</span></span> <span data-ttu-id="02da4-125">此邏輯的設計目的是要提供在您的組織中執行和測試動作的最準確會計。</span><span class="sxs-lookup"><span data-stu-id="02da4-125">This logic is designed to provide the most accurate accounting of how actions are implemented and tested in your organization.</span></span> <span data-ttu-id="02da4-126">您可能會注意到，這可能會導致您的整體合規性分數與評估分數的平均不同。</span><span class="sxs-lookup"><span data-stu-id="02da4-126">You may notice that this can cause your overall compliance score to differ from the average of your assessment scores.</span></span> <span data-ttu-id="02da4-127">請閱讀下列有關 [如何對動作進行計分的](#action-types-and-points)詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="02da4-127">Read more below about [how actions are scored](#action-types-and-points).</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="02da4-128">根據 Microsoft 365 資料保護基準的初始分數</span><span class="sxs-lookup"><span data-stu-id="02da4-128">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="02da4-129">合規性管理員會根據 Microsoft 365 資料保護基準，為您提供初始分數。</span><span class="sxs-lookup"><span data-stu-id="02da4-129">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="02da4-130">此基準是一組控制項，包含資料保護和一般資料控管的重要規章和標準。</span><span class="sxs-lookup"><span data-stu-id="02da4-130">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="02da4-131">此基線主要從 NIST CSF，主要從 NIST (中繪製元素。) 和 ISO (國際性組織的標準化) ，以及 FedRAMP (聯邦風險和授權管理計畫) 和 GDPR (歐盟) 的一般資料保護法規。</span><span class="sxs-lookup"><span data-stu-id="02da4-131">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="02da4-132">根據提供給所有組織的預設資料保護基準評估，計算您的初始分數。</span><span class="sxs-lookup"><span data-stu-id="02da4-132">Your initial score is calculated according to the default Data Protection Baseline assessment provided to all organizations.</span></span> <span data-ttu-id="02da4-133">在您第一次造訪時，合規性管理員已經從您的 Microsoft 365 解決方案中收集信號。</span><span class="sxs-lookup"><span data-stu-id="02da4-133">Upon your first visit, Compliance Manager is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="02da4-134">您將會很快看到組織相對於重要資料保護標準與法規的執行方式，並查看建議採取的改進動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-134">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="02da4-135">因為每個組織都有特定需求，所以合規性管理員必須視您設定及管理評估，以盡可能將風險降至最低並盡可能降低。</span><span class="sxs-lookup"><span data-stu-id="02da4-135">Because every organization has specific needs, Compliance Manager relies on you to set up and manage assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="how-compliance-manager-continuously-assesses-controls"></a><span data-ttu-id="02da4-136">合規性管理員如何持續評估控制項</span><span class="sxs-lookup"><span data-stu-id="02da4-136">How Compliance Manager continuously assesses controls</span></span>

<span data-ttu-id="02da4-137">合規性管理員會自動掃描您的 Microsoft 365 環境，並偵測您的系統設定，持續並自動更新您的技術動作狀態。</span><span class="sxs-lookup"><span data-stu-id="02da4-137">Compliance Manager automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical action status.</span></span> <span data-ttu-id="02da4-138">Microsoft Secure 得分是執行監控的基礎引擎。</span><span class="sxs-lookup"><span data-stu-id="02da4-138">Microsoft Secure Score is the underlying engine that performs the monitoring.</span></span>

<span data-ttu-id="02da4-139">您的儀表板每24小時就會更新一次動作狀態。</span><span class="sxs-lookup"><span data-stu-id="02da4-139">Your action status is updated on your dashboard every 24 hours.</span></span> <span data-ttu-id="02da4-140">一旦您遵循執行控制項的建議，您通常會在下一天看到控制項狀態已更新。</span><span class="sxs-lookup"><span data-stu-id="02da4-140">Once you follow a recommendation to implement a control, you’ll typically see the control status updated the next day.</span></span>

<span data-ttu-id="02da4-141">例如，如果您在 Azure AD 入口網站中開啟多重要素驗證 (MFA) ，合規性管理員會偵測設定，並將其反映在控制存取解決方案的詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="02da4-141">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Manager detects the setting and reflects it in the control access solution details.</span></span> <span data-ttu-id="02da4-142">相反地，如果您未開啟 MFA，合規性管理員旗標為您採取建議的動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-142">Conversely, if you didn’t turn on MFA, Compliance Manager flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="02da4-143">深入瞭解 [安全性分數及其運作方式](../security/defender/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="02da4-143">Learn more about [Secure Score and how it works](../security/defender/microsoft-secure-score.md).</span></span>
  
## <a name="action-types-and-points"></a><span data-ttu-id="02da4-144">動作類型和點</span><span class="sxs-lookup"><span data-stu-id="02da4-144">Action types and points</span></span>

<span data-ttu-id="02da4-145">合規性管理員追蹤兩種類型的動作：</span><span class="sxs-lookup"><span data-stu-id="02da4-145">Compliance Manager tracks two types of actions:</span></span>

1. <span data-ttu-id="02da4-146">**您的改善動作**：您的組織管理的動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-146">**Your improvement actions**: actions that your organization manages.</span></span>
2. <span data-ttu-id="02da4-147">**Microsoft 動作**： microsoft 管理的動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-147">**Microsoft actions**: actions that Microsoft manages.</span></span>

<span data-ttu-id="02da4-148">這兩種類型的動作都會在完成時算作整體分數。</span><span class="sxs-lookup"><span data-stu-id="02da4-148">Both types of actions have points that count toward your overall score when completed.</span></span>

### <a name="technical-and-non-technical-actions"></a><span data-ttu-id="02da4-149">技術和非技術動作</span><span class="sxs-lookup"><span data-stu-id="02da4-149">Technical and non-technical actions</span></span>

<span data-ttu-id="02da4-150">動作的分組方式不論是技術或非技術性質。</span><span class="sxs-lookup"><span data-stu-id="02da4-150">Actions are grouped by whether they are technical or non-technical in nature.</span></span> <span data-ttu-id="02da4-151">每個動作的計分影響依類型而有所不同。</span><span class="sxs-lookup"><span data-stu-id="02da4-151">The scoring impact of each action differs by type.</span></span>

- <span data-ttu-id="02da4-152">**技術動作** 的實施方式是與方案的技術互動 (例如，變更設定) 。</span><span class="sxs-lookup"><span data-stu-id="02da4-152">**Technical actions** are implemented by interacting with the technology of a solution (for example, changing a configuration).</span></span> <span data-ttu-id="02da4-153">每個動作只會授與技術動作點一次，不論其所屬的群組數目為何。</span><span class="sxs-lookup"><span data-stu-id="02da4-153">The points for technical actions are granted once per action, regardless of how many groups it belongs to.</span></span>

- <span data-ttu-id="02da4-154">**非技術動作** 是由您的組織管理，並以不使用解決方案技術的方式來執行。</span><span class="sxs-lookup"><span data-stu-id="02da4-154">**Non-technical actions** are managed by your organization and implemented in ways other than working with the technology of a solution.</span></span> <span data-ttu-id="02da4-155">非技術動作的類型有兩種： **檔** 與 **運作**。</span><span class="sxs-lookup"><span data-stu-id="02da4-155">There are two types of non-technical actions: **documentation** and **operational**.</span></span> <span data-ttu-id="02da4-156">這些動作的點會套用至群組層級的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="02da4-156">The points for these actions are applied to your compliance score at a group level.</span></span> <span data-ttu-id="02da4-157">這表示如果有多個群組中的動作，當您每次在群組中執行它時，您會收到該動作的 point 值。</span><span class="sxs-lookup"><span data-stu-id="02da4-157">This means that if an action exists in multiple groups, you will receive the action's point value each time you implement it within a group.</span></span>

<span data-ttu-id="02da4-158">**技術和非技術動作計分的範例：**</span><span class="sxs-lookup"><span data-stu-id="02da4-158">**Example of how technical and non-technical actions are scored:**</span></span>

<span data-ttu-id="02da4-159">假設您的技術動作相當於5群組中的3點，而您的非技術動作值得三分，但在相同5個群組中有。</span><span class="sxs-lookup"><span data-stu-id="02da4-159">Let's say you have a technical action worth 3 points that exists in 5 groups, and you have a non-technical action worth 3 points that exists in the same 5 groups.</span></span>

<span data-ttu-id="02da4-160">如果您成功執行技術動作，您收到的點數總數為3。</span><span class="sxs-lookup"><span data-stu-id="02da4-160">If you successfully implement the technical action, the total number of points you receive is 3.</span></span> <span data-ttu-id="02da4-161">這是因為您只需要針對租使用者執行一次該動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-161">This is because you only need to implement the action once for your tenant.</span></span> <span data-ttu-id="02da4-162">技術動作的「實施」和「測試」狀態會在該動作的所有實例中顯示相同的專案。</span><span class="sxs-lookup"><span data-stu-id="02da4-162">The implementation and test status for the technical action will show the same in all instances of that action, in every group it belongs to.</span></span>

<span data-ttu-id="02da4-163">如果您已在5個群組中成功地執行非技術動作，您收到的點數總數為15。</span><span class="sxs-lookup"><span data-stu-id="02da4-163">If you successfully implement the non-technical action in each of the 5 groups, the total number of points you receive is 15.</span></span> <span data-ttu-id="02da4-164">這是因為您必須在每個群組中執行動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-164">This is because you need to implement the action in each group.</span></span> <span data-ttu-id="02da4-165">非技術動作的實施和測試狀態會因群組而異，因為其各個群組內會分開執行該動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-165">The implementation and test status for the non-technical action will differ across groups because the action is implemented separately within each of its groups.</span></span>

<span data-ttu-id="02da4-166">這個計分邏輯的設計目的是為了提供在組織中執行和測試動作的最準確的會計。</span><span class="sxs-lookup"><span data-stu-id="02da4-166">This scoring logic is designed to provide the most accurate accounting of how actions are implemented and tested in your organization.</span></span>

### <a name="how-score-values-are-determined"></a><span data-ttu-id="02da4-167">決定計分值的方式</span><span class="sxs-lookup"><span data-stu-id="02da4-167">How score values are determined</span></span>
 
<span data-ttu-id="02da4-168">會根據動作為強制或選擇性，以及是否為預防性、偵探或糾正動作，指派分數值。</span><span class="sxs-lookup"><span data-stu-id="02da4-168">Actions are assigned a score value based on whether they’re mandatory or discretionary, and whether they’re preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-actions"></a><span data-ttu-id="02da4-169">強制和自由的動作</span><span class="sxs-lookup"><span data-stu-id="02da4-169">Mandatory and discretionary actions</span></span>

 - <span data-ttu-id="02da4-170">不能故意或無意中略過強制執行的 **動作**。</span><span class="sxs-lookup"><span data-stu-id="02da4-170">**Mandatory actions** can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="02da4-171">強制執行動作的範例是一個集中管理的密碼原則，可設定密碼長度、複雜性和到期的需求。</span><span class="sxs-lookup"><span data-stu-id="02da4-171">An example of a mandatory action is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="02da4-172">使用者必須遵循這些需求來存取系統。</span><span class="sxs-lookup"><span data-stu-id="02da4-172">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="02da4-173">**自由動作** 會依據使用者來瞭解和遵循原則。</span><span class="sxs-lookup"><span data-stu-id="02da4-173">**Discretionary actions** rely upon users to understand and adhere to a policy.</span></span> <span data-ttu-id="02da4-174">比方說，要求使用者在離開座位前鎖定電腦就是選擇型動作的原則，因為它需要仰賴使用者的配合。</span><span class="sxs-lookup"><span data-stu-id="02da4-174">For example, a policy requiring users to lock their computer when they leave it is a discretionary action because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-actions"></a><span data-ttu-id="02da4-175">預防性、偵探和修正動作</span><span class="sxs-lookup"><span data-stu-id="02da4-175">Preventative, detective, and corrective actions</span></span>
  
 - <span data-ttu-id="02da4-176">**預防型動作** 可處理特定風險。</span><span class="sxs-lookup"><span data-stu-id="02da4-176">**Preventative actions** address specific risks.</span></span> <span data-ttu-id="02da4-177">舉例來說，使用加密來保護資訊就是針對攻擊和資料外洩等風險的預防型動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-177">For example, protecting information at rest using encryption is a preventative action against attacks and breaches.</span></span> <span data-ttu-id="02da4-178">職責分工是管理利益衝突及防堵詐騙的預防型動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-178">Separation of duties is a preventative action to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="02da4-179">**偵探動作** 主動監視系統，以找出未規律的條件或行為，以找出風險或可能用來偵測入侵或違規的行為。</span><span class="sxs-lookup"><span data-stu-id="02da4-179">**Detective actions** actively monitor systems to identify irregular conditions or behaviors that represent risk, or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="02da4-180">範例包括系統存取審核和特權管理動作。</span><span class="sxs-lookup"><span data-stu-id="02da4-180">Examples include system access auditing and privileged administrative actions.</span></span> <span data-ttu-id="02da4-181">法規遵從性審核是一種可用於尋找處理常式問題的偵探動作類型。</span><span class="sxs-lookup"><span data-stu-id="02da4-181">Regulatory compliance audits are a type of detective action used to find process issues.</span></span>
  
- <span data-ttu-id="02da4-182">**糾正動作** 會嘗試將安全性事件的不利影響降至最低，採取糾正動作來降低立即效果，並盡可能將損毀。</span><span class="sxs-lookup"><span data-stu-id="02da4-182">**Corrective actions** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="02da4-183">隱私權事件回應是一種矯正型動作，會在遭到侵害後限制損傷並將系統還原至可以運作的狀態。</span><span class="sxs-lookup"><span data-stu-id="02da4-183">Privacy incident response is a corrective action to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="02da4-184">在合規性管理員中，每個動作都會以其所代表的風險指派值：</span><span class="sxs-lookup"><span data-stu-id="02da4-184">Each action has an assigned value in Compliance Manager based on the risk it represents:</span></span>

|<span data-ttu-id="02da4-185">**類型**</span><span class="sxs-lookup"><span data-stu-id="02da4-185">**Type**</span></span>|<span data-ttu-id="02da4-186">**指派分數**</span><span class="sxs-lookup"><span data-stu-id="02da4-186">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="02da4-187">預防性強制</span><span class="sxs-lookup"><span data-stu-id="02da4-187">Preventative mandatory</span></span> | <span data-ttu-id="02da4-188">7</span><span class="sxs-lookup"><span data-stu-id="02da4-188">27</span></span> |
| <span data-ttu-id="02da4-189">預防選擇型</span><span class="sxs-lookup"><span data-stu-id="02da4-189">Preventative discretionary</span></span> | <span data-ttu-id="02da4-190">9 </span><span class="sxs-lookup"><span data-stu-id="02da4-190">9</span></span> |
| <span data-ttu-id="02da4-191">偵探強制</span><span class="sxs-lookup"><span data-stu-id="02da4-191">Detective mandatory</span></span> | <span data-ttu-id="02da4-192">3 </span><span class="sxs-lookup"><span data-stu-id="02da4-192">3</span></span> |
| <span data-ttu-id="02da4-193">偵探自由</span><span class="sxs-lookup"><span data-stu-id="02da4-193">Detective discretionary</span></span> | <span data-ttu-id="02da4-194">1 </span><span class="sxs-lookup"><span data-stu-id="02da4-194">1</span></span> |
| <span data-ttu-id="02da4-195">強制矯正型</span><span class="sxs-lookup"><span data-stu-id="02da4-195">Corrective mandatory</span></span> | <span data-ttu-id="02da4-196">3 </span><span class="sxs-lookup"><span data-stu-id="02da4-196">3</span></span> |
| <span data-ttu-id="02da4-197">隨機糾正</span><span class="sxs-lookup"><span data-stu-id="02da4-197">Corrective discretionary</span></span> | <span data-ttu-id="02da4-198">1 </span><span class="sxs-lookup"><span data-stu-id="02da4-198">1</span></span> |
  
<span data-ttu-id="02da4-199">![合規性管理員動作點值](../media/compliance-score-action-scoring.png "合規性管理員動作點值")</span><span class="sxs-lookup"><span data-stu-id="02da4-199">![Compliance Manager action point values](../media/compliance-score-action-scoring.png "Compliance Manager action point values")</span></span>