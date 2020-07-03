---
title: Microsoft 規範分數（預覽）計算
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
description: 瞭解 Microsoft 合規性分數如何根據採取的措施來計算個人化分數，並改善您的相容性狀況。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024673"
---
# <a name="compliance-score-preview-calculation"></a><span data-ttu-id="7e2fb-103">合規性分數（預覽）計算</span><span class="sxs-lookup"><span data-stu-id="7e2fb-103">Compliance Score (preview) calculation</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e2fb-104">您不應將「合規性分數」和「合規性管理員」中的建議視為合規性的保證。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-104">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="7e2fb-105">您可以根據法規環境評估和驗證客戶控制措施的效能。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-105">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="7e2fb-106">這些服務目前是在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-106">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="7e2fb-107">另請參閱[Microsoft 365 授權指南以取得安全性和合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-107">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="how-compliance-score-works"></a><span data-ttu-id="7e2fb-108">合規性分數的運作方式</span><span class="sxs-lookup"><span data-stu-id="7e2fb-108">How Compliance Score works</span></span>

<span data-ttu-id="7e2fb-109">合規性分數儀表板會顯示分數，以度量您在控制項中完成改進動作的進度。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="7e2fb-110">每個動作對您的分數有不同的影響，取決於可能的風險。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-110">Each action has a different impact on your score, depending on the potential risks involved.</span></span> <span data-ttu-id="7e2fb-111">您的分數可協助您決定關注的動作，以改善您的整體相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-111">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="7e2fb-112">在*整個分數中*，會以通過/失敗的方式，將控制項顯示的符合性分數值整體套用到總分。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-112">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="7e2fb-113">控制項已執行並通過後續的評估測試，否則不會。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-113">Either the control is implemented and passes the subsequent assessment test, or it doesn't.</span></span> 

<span data-ttu-id="7e2fb-114">當控制項具有下列專案時，會將點加入至您的規範分數。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-114">Points are added to your compliance score when the control has:</span></span>

- <span data-ttu-id="7e2fb-115">**實施狀態**等於 [已**實現**] 或 [**替代] 實施**，以及</span><span class="sxs-lookup"><span data-stu-id="7e2fb-115">**Implementation Status** equals **Implemented** or **Alternative Implementation**, and</span></span>
- <span data-ttu-id="7e2fb-116">已**通過\*\*\*\*測試結果**equals。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-116">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="7e2fb-117">控制項總分是採取改進動作所取得的點數總和。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-117">A control score is the sum of points earned by taking improvement actions.</span></span> <span data-ttu-id="7e2fb-118">您的控制分數總和是評估分數。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-118">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="7e2fb-119">**您的評估分數總和是您的整體合規性分數。**</span><span class="sxs-lookup"><span data-stu-id="7e2fb-119">**The sum of your assessment scores is your overall compliance score.**</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="7e2fb-120">以 Microsoft 365 資料保護基準為基礎的初始分數</span><span class="sxs-lookup"><span data-stu-id="7e2fb-120">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="7e2fb-121">合規性分數為您提供以 Microsoft 365 資料保護基準為基礎的初始分數。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-121">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="7e2fb-122">此基準是一組控制項，包含資料保護和一般資料控管的重要規章和標準。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-122">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="7e2fb-123">此基準主要是從 NIST CSF （國家標準和技術協會 Cybersecurity Framework）和 ISO （國際標準組織的標準化 FedRAMP）和 GDPR （歐盟的一般資料保護法規）和（一般資料保護法規）中的專案來繪製要素。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-123">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="7e2fb-124">資料保護基準評估（預設為所有組織提供）是在您設定其他評估之前，用來計算您的初始分數。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-124">The data protection baseline assessment (provided by default to all organizations) is used to calculate your initial score before you configure any other assessments.</span></span> <span data-ttu-id="7e2fb-125">在您第一次造訪時，合規性分數已經從您的 Microsoft 365 解決方案中收集信號。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-125">Upon your first visit, Compliance Score is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="7e2fb-126">您將會很快看到組織相對於重要資料保護標準與法規的執行方式，並查看建議採取的改進動作。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-126">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="7e2fb-127">由於每個組織都有特定需求，因此符合您的需求取決於您設定及管理您自己的評估，以協助盡可能縮小及緩解風險。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-127">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="7e2fb-128">合規性分數不斷評估控制措施的方式</span><span class="sxs-lookup"><span data-stu-id="7e2fb-128">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="7e2fb-129">合規性分數會透過您的 Microsoft 365 環境自動掃描，並偵測您的系統設定，持續並自動更新您的技術控制狀態。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-129">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="7e2fb-130">安全評分是執行監控的基礎引擎。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-130">Secure Score is the underlying engine that performs the monitoring.</span></span>

<span data-ttu-id="7e2fb-131">您的控制狀態會在您的合規性分數儀表板上每隔24小時更新。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-131">Your control status is updated on your Compliance Score dashboard every 24 hours.</span></span> <span data-ttu-id="7e2fb-132">當您遵循執行控制項的建議後，您將會在下一天看到控制項狀態已更新。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-132">Once you follow a recommendation to implement a control, you'll see the control status updated the next day.</span></span>

<span data-ttu-id="7e2fb-133">例如，如果您在 Azure AD 入口網站中開啟多重要素驗證（MFA），合規性分數會偵測設定，並反映在控制存取解決方案的詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-133">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="7e2fb-134">相反地，如果您未開啟 MFA，請將合規性分數旗標視為建議採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-134">Conversely, if you didn't turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="7e2fb-135">在公開預覽期間，連續的評估可供部分控制項使用，但並非全部。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-135">During public preview, continuous assessment is available to a portion of controls, but not all.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="7e2fb-136">深入了解</span><span class="sxs-lookup"><span data-stu-id="7e2fb-136">Learn more</span></span>
<span data-ttu-id="7e2fb-137">[閱讀安全分數及其運作方式](../security/mtp/microsoft-secure-score-new.md)。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-137">[Read about Secure Score and how it works](../security/mtp/microsoft-secure-score-new.md).</span></span>
  
## <a name="action-types-and-points"></a><span data-ttu-id="7e2fb-138">動作類型和點</span><span class="sxs-lookup"><span data-stu-id="7e2fb-138">Action types and points</span></span>

<span data-ttu-id="7e2fb-139">合規性分數追蹤兩種類型的動作：您管理的動作，以及 Microsoft 所管理的動作。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-139">Compliance Score tracks two types of actions: actions you manage, and actions Microsoft manages.</span></span> <span data-ttu-id="7e2fb-140">這兩種類型的動作都會在完成時算作整體分數的點數：</span><span class="sxs-lookup"><span data-stu-id="7e2fb-140">Both types of actions have points that count toward your overall score when completed:</span></span>

1. <span data-ttu-id="7e2fb-141">**您的分數**取決於您的組織所管理的控制項的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-141">**Your points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="7e2fb-142">**Microsoft 受管理點**根據 Microsoft 以雲端服務提供者所管理的動作來貢獻您的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-142">**Microsoft managed points** contribute to your compliance score based on actions managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="7e2fb-143">會根據動作為強制或選擇性，以及是否為預防性、偵探或糾正動作，指派分數值。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-143">Actions are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-actions"></a><span data-ttu-id="7e2fb-144">強制和自由的動作</span><span class="sxs-lookup"><span data-stu-id="7e2fb-144">Mandatory and discretionary actions</span></span>

 - <span data-ttu-id="7e2fb-145">不能故意或無意中略過強制執行的**動作**。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-145">**Mandatory actions** can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="7e2fb-146">範例是設定密碼長度、複雜性和到期設定需求的集中式管理密碼原則。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-146">An example is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="7e2fb-147">使用者必須遵循這些需求，才能存取系統。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-147">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="7e2fb-148">**自由動作**視使用者來瞭解原則，並採取相應的動作。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-148">**Discretionary actions** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="7e2fb-149">例如，如果原則要求使用者在其保留時鎖定其電腦，則其為自由的動作，因為它會因使用者而異。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-149">For example, a policy requiring users to lock their computer when they leave it is a discretionary action because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-actions"></a><span data-ttu-id="7e2fb-150">預防性、偵探和修正動作</span><span class="sxs-lookup"><span data-stu-id="7e2fb-150">Preventative, detective, and corrective actions</span></span>
  
 - <span data-ttu-id="7e2fb-151">**預防動作**會解決特定風險。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-151">**Preventative actions** address specific risks.</span></span> <span data-ttu-id="7e2fb-152">例如，使用加密來保護靜止的資訊，是防範攻擊和違規行為的預防措施。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-152">For example, protecting information at rest using encryption is a preventative action against attacks and breaches.</span></span> <span data-ttu-id="7e2fb-153">劃分職責是一項預防性動作，可管理利益衝突並防範欺詐行為。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-153">Separation of duties is a preventative action to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="7e2fb-154">**偵探動作**主動監視系統，以找出未規律的條件或行為，以找出風險或可能用來偵測入侵或違規的行為。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-154">**Detective actions** actively monitor systems to identify irregular conditions or behaviors that represent risk, or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="7e2fb-155">範例包括系統存取審核和特權管理動作。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-155">Examples include system access auditing and privileged administrative actions.</span></span> <span data-ttu-id="7e2fb-156">法規遵從性審核是一種可用於尋找處理常式問題的偵探動作類型。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-156">Regulatory compliance audits are a type of detective action used to find process issues.</span></span>
  
- <span data-ttu-id="7e2fb-157">**糾正動作**會嘗試將安全性事件的不利影響降至最低，採取糾正動作來降低立即效果，並盡可能將損毀。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-157">**Corrective actions** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="7e2fb-158">隱私權事件回應是一種糾正動作，可在損毀後，將損毀和還原系統限制在運作狀態。</span><span class="sxs-lookup"><span data-stu-id="7e2fb-158">Privacy incident response is a corrective action to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="7e2fb-159">每個動作都根據其所代表的風險，以合規性分數指派值：</span><span class="sxs-lookup"><span data-stu-id="7e2fb-159">Each action has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="7e2fb-160">**類型**</span><span class="sxs-lookup"><span data-stu-id="7e2fb-160">**Type**</span></span>|<span data-ttu-id="7e2fb-161">**指派分數**</span><span class="sxs-lookup"><span data-stu-id="7e2fb-161">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="7e2fb-162">預防性強制</span><span class="sxs-lookup"><span data-stu-id="7e2fb-162">Preventative mandatory</span></span> | <span data-ttu-id="7e2fb-163">7</span><span class="sxs-lookup"><span data-stu-id="7e2fb-163">27</span></span> |
| <span data-ttu-id="7e2fb-164">預防自由</span><span class="sxs-lookup"><span data-stu-id="7e2fb-164">Preventative discretionary</span></span> | <span data-ttu-id="7e2fb-165">9 </span><span class="sxs-lookup"><span data-stu-id="7e2fb-165">9</span></span> |
| <span data-ttu-id="7e2fb-166">偵探強制</span><span class="sxs-lookup"><span data-stu-id="7e2fb-166">Detective mandatory</span></span> | <span data-ttu-id="7e2fb-167">3 </span><span class="sxs-lookup"><span data-stu-id="7e2fb-167">3</span></span> |
| <span data-ttu-id="7e2fb-168">偵探自由</span><span class="sxs-lookup"><span data-stu-id="7e2fb-168">Detective discretionary</span></span> | <span data-ttu-id="7e2fb-169">1 </span><span class="sxs-lookup"><span data-stu-id="7e2fb-169">1</span></span> |
| <span data-ttu-id="7e2fb-170">必要修正</span><span class="sxs-lookup"><span data-stu-id="7e2fb-170">Corrective mandatory</span></span> | <span data-ttu-id="7e2fb-171">3 </span><span class="sxs-lookup"><span data-stu-id="7e2fb-171">3</span></span> |
| <span data-ttu-id="7e2fb-172">隨機糾正</span><span class="sxs-lookup"><span data-stu-id="7e2fb-172">Corrective discretionary</span></span> | <span data-ttu-id="7e2fb-173">1 </span><span class="sxs-lookup"><span data-stu-id="7e2fb-173">1</span></span> |
  
<span data-ttu-id="7e2fb-174">![合規性分數控制點值](../media/compliance-score-controls-scoring.png "合規性分數控制點值")</span><span class="sxs-lookup"><span data-stu-id="7e2fb-174">![Compliance Score controls point values](../media/compliance-score-controls-scoring.png "Compliance Score controls point values")</span></span>