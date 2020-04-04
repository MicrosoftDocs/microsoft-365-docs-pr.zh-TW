---
title: 合規性分數計算
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
ms.openlocfilehash: 10e75be9541c4bd2b5a62d8bea46c45d213655e2
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141580"
---
# <a name="microsoft-compliance-score-preview-calculation"></a><span data-ttu-id="dd97e-103">Microsoft 規範分數（預覽）計算</span><span class="sxs-lookup"><span data-stu-id="dd97e-103">Microsoft Compliance Score (preview) calculation</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd97e-104">合規性分數不會明確組織符合任何特定標準或法規的絕對度量。</span><span class="sxs-lookup"><span data-stu-id="dd97e-104">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="dd97e-105">它表示您已採用控制的程度，可降低個人資料和個別隱私權的風險。</span><span class="sxs-lookup"><span data-stu-id="dd97e-105">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="dd97e-106">符合性分數和合規性管理員的建議不得加以轉譯以保證法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="dd97e-106">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="dd97e-107">這項服務目前在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。</span><span class="sxs-lookup"><span data-stu-id="dd97e-107">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="overview"></a><span data-ttu-id="dd97e-108">概觀</span><span class="sxs-lookup"><span data-stu-id="dd97e-108">Overview</span></span>

<span data-ttu-id="dd97e-109">合規性分數儀表板會顯示分數，以度量您在控制項中完成改進動作的進度。</span><span class="sxs-lookup"><span data-stu-id="dd97e-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="dd97e-110">當您完成動作時，您的點數便會累算。</span><span class="sxs-lookup"><span data-stu-id="dd97e-110">Your points accrue when you complete actions.</span></span>

<span data-ttu-id="dd97e-111">您的分數是根據 Microsoft 管理的動作和客戶管理的動作的完成而計算。</span><span class="sxs-lookup"><span data-stu-id="dd97e-111">Your score is calculated based on the completion of Microsoft-managed actions and customer-managed actions.</span></span> <span data-ttu-id="dd97e-112">每個動作對您的分數有不同的影響，取決於可能的風險。</span><span class="sxs-lookup"><span data-stu-id="dd97e-112">Each action has a different impact on your score, depending on the potential risks involved.</span></span> <span data-ttu-id="dd97e-113">您的分數可協助您決定關注的動作，以改善您的整體相容性狀況。</span><span class="sxs-lookup"><span data-stu-id="dd97e-113">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="dd97e-114">在*整個分數中*，會以通過/失敗的方式，將控制項顯示的符合性分數值整體套用到總分。</span><span class="sxs-lookup"><span data-stu-id="dd97e-114">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="dd97e-115">控制項已執行並通過後續的評估測試，否則不會執行。</span><span class="sxs-lookup"><span data-stu-id="dd97e-115">Either the control is implemented and passes the subsequent assessment test, or it does not.</span></span> <span data-ttu-id="dd97e-116">當控制項具有下列專案時，已指派的點會新增至符合性分數：</span><span class="sxs-lookup"><span data-stu-id="dd97e-116">Assigned points are added to Compliance Score when the control has:</span></span>

- <span data-ttu-id="dd97e-117">**實施狀態**等於 [已**實現**] 或 [**替代] 實施**，以及</span><span class="sxs-lookup"><span data-stu-id="dd97e-117">**Implementation Status** equals **Implemented** or **Alternative Implementation** and,</span></span>
- <span data-ttu-id="dd97e-118">已**通過\*\*\*\*測試結果**equals。</span><span class="sxs-lookup"><span data-stu-id="dd97e-118">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="dd97e-119">採取改進動作所取得的點數總和是控制分數。</span><span class="sxs-lookup"><span data-stu-id="dd97e-119">The sum of points earned by taking improvement actions is the control score.</span></span> <span data-ttu-id="dd97e-120">您的控制分數總和是評估分數。</span><span class="sxs-lookup"><span data-stu-id="dd97e-120">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="dd97e-121">您的評估分數總和是您的整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="dd97e-121">The sum of your assessment scores is your overall compliance score</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="dd97e-122">以 Microsoft 365 資料保護基準為基礎的初始分數</span><span class="sxs-lookup"><span data-stu-id="dd97e-122">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="dd97e-123">合規性分數可讓您根據 Microsoft 365 資料保護基準（一組包含重要的資料保護和一般資料控管的主要法規和標準），為您提供初始分數。</span><span class="sxs-lookup"><span data-stu-id="dd97e-123">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline, which is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="dd97e-124">此基準主要是從 NIST CSF （國家標準和技術協會 Cybersecurity Framework）和 ISO （國際標準組織的標準化 FedRAMP）和 GDPR （歐盟的一般資料保護法規）和（一般資料保護法規）中的專案來繪製要素。</span><span class="sxs-lookup"><span data-stu-id="dd97e-124">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="dd97e-125">合規性分數不斷評估控制措施的方式</span><span class="sxs-lookup"><span data-stu-id="dd97e-125">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="dd97e-126">合規性分數會透過您的 Microsoft 365 環境自動掃描，並偵測您的系統設定，持續並自動更新您的技術控制狀態。</span><span class="sxs-lookup"><span data-stu-id="dd97e-126">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="dd97e-127">安全評分是執行監控的基礎引擎。</span><span class="sxs-lookup"><span data-stu-id="dd97e-127">Secure Score is the underlying engine that performs the monitoring.</span></span> <span data-ttu-id="dd97e-128">[深入瞭解安全性分數及其運作方式](../security/mtp/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="dd97e-128">[Learn more about Secure Score and how it works](../security/mtp/microsoft-secure-score.md).</span></span>

<span data-ttu-id="dd97e-129">您的控制狀態會在您的合規性分數儀表板上每隔24小時更新。</span><span class="sxs-lookup"><span data-stu-id="dd97e-129">Your control status is updated on your Compliance Score dashboard every 24 hours.</span></span> <span data-ttu-id="dd97e-130">當您遵循執行控制項的建議後，您將會在下一天看到控制項狀態已更新。</span><span class="sxs-lookup"><span data-stu-id="dd97e-130">Once you follow a recommendation to implement a control, you'll see the control status updated the next day.</span></span>

<span data-ttu-id="dd97e-131">例如，如果您在 Azure AD 入口網站中開啟多重要素驗證（MFA），合規性分數會偵測設定，並反映在控制存取解決方案的詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="dd97e-131">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="dd97e-132">相反地，如果您未開啟 MFA，請將合規性分數旗標視為建議採取的動作。</span><span class="sxs-lookup"><span data-stu-id="dd97e-132">Conversely, if you didn't turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="dd97e-133">在公開預覽期間，連續的評估可供部分控制項使用，但並非全部。</span><span class="sxs-lookup"><span data-stu-id="dd97e-133">During public preview, continuous assessment is available to a portion of controls, but not all.</span></span>
  
## <a name="control-types-and-points"></a><span data-ttu-id="dd97e-134">控制項類型和點</span><span class="sxs-lookup"><span data-stu-id="dd97e-134">Control types and points</span></span>

<span data-ttu-id="dd97e-135">合規性分數追蹤兩種類型的控制項：「Microsoft 管理」和「客戶管理」，每個控制項都有分數可貢獻您的整體分數：</span><span class="sxs-lookup"><span data-stu-id="dd97e-135">Compliance Score tracks two types of controls—Microsoft-managed and customer-managed—each of which have points that contribute to your overall score:</span></span>

1. <span data-ttu-id="dd97e-136">**客戶管理的點**會根據您的組織所管理的控制項，來貢獻您的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="dd97e-136">**Customer-managed points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="dd97e-137">根據 Microsoft 以雲端服務提供者所管理的控制項， **microsoft 受管理的點**會為您的合規性分數貢獻。</span><span class="sxs-lookup"><span data-stu-id="dd97e-137">**Microsoft-managed points** contribute to your compliance score based on controls managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="dd97e-138">控制項會根據其是否為強制性或自由的，以及是否為預防性、偵探或糾正，指派分數值。</span><span class="sxs-lookup"><span data-stu-id="dd97e-138">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-controls"></a><span data-ttu-id="dd97e-139">強制和自由控制</span><span class="sxs-lookup"><span data-stu-id="dd97e-139">Mandatory and discretionary controls</span></span>

 - <span data-ttu-id="dd97e-140">**強制控制項**是指無法略過的動作，不論是有意或無意。</span><span class="sxs-lookup"><span data-stu-id="dd97e-140">**Mandatory controls** are actions that can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="dd97e-141">範例是設定密碼長度、複雜性和到期設定需求的集中式管理密碼原則。</span><span class="sxs-lookup"><span data-stu-id="dd97e-141">An example is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="dd97e-142">使用者必須遵循這些需求，才能存取系統。</span><span class="sxs-lookup"><span data-stu-id="dd97e-142">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="dd97e-143">**自由的控制項**會依據使用者來瞭解原則，並採取相應的動作。</span><span class="sxs-lookup"><span data-stu-id="dd97e-143">**Discretionary controls** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="dd97e-144">例如，如果原則要求使用者在其離開時鎖定其電腦，則其為自由控制項，因為它會因使用者而異。</span><span class="sxs-lookup"><span data-stu-id="dd97e-144">For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-controls"></a><span data-ttu-id="dd97e-145">預防性、偵探和修正控制措施</span><span class="sxs-lookup"><span data-stu-id="dd97e-145">Preventative, detective, and corrective controls</span></span>
  
 - <span data-ttu-id="dd97e-146">**預防控制措施**解決特定風險。</span><span class="sxs-lookup"><span data-stu-id="dd97e-146">**Preventative controls** address specific risks.</span></span> <span data-ttu-id="dd97e-147">例如，使用加密來保護靜態資訊，是防範攻擊和違規行為的預防控制措施。</span><span class="sxs-lookup"><span data-stu-id="dd97e-147">For example, protecting information at rest using encryption is a preventative control against attacks and breaches.</span></span> <span data-ttu-id="dd97e-148">劃分職責是一種預防控制，可管理利益衝突，並防止欺詐。</span><span class="sxs-lookup"><span data-stu-id="dd97e-148">Separation of duties is a preventative control to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="dd97e-149">**偵探控制**主動監視系統，以找出未規律的條件或行為，以找出風險或可能用來偵測入侵或違規的行為。</span><span class="sxs-lookup"><span data-stu-id="dd97e-149">**Detective controls** actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="dd97e-150">「系統存取審核」和「特權管理動作」審核是「偵探監控」控制項的類型。</span><span class="sxs-lookup"><span data-stu-id="dd97e-150">System access auditing and privileged administrative actions auditing are types of detective monitoring controls.</span></span> <span data-ttu-id="dd97e-151">法規遵從性審核是一種可用於尋找處理問題的偵探控制項類型。</span><span class="sxs-lookup"><span data-stu-id="dd97e-151">Regulatory compliance audits are a type of detective control used to find process issues.</span></span>
  
- <span data-ttu-id="dd97e-152">**修正控制**會嘗試將安全性事件的不利影響降至最低，採取糾正動作以減少立即影響，並在可能的情況下反轉損毀。</span><span class="sxs-lookup"><span data-stu-id="dd97e-152">**Corrective controls** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="dd97e-153">隱私權事件回應是一種修正控制，可在損毀後，將損毀和還原系統限制在運作狀態。</span><span class="sxs-lookup"><span data-stu-id="dd97e-153">Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="dd97e-154">根據所代表的風險，每個控制項都有指派的合規性分數中的值：</span><span class="sxs-lookup"><span data-stu-id="dd97e-154">Each control has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="dd97e-155">**類型**</span><span class="sxs-lookup"><span data-stu-id="dd97e-155">**Type**</span></span>|<span data-ttu-id="dd97e-156">**指派分數**</span><span class="sxs-lookup"><span data-stu-id="dd97e-156">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="dd97e-157">預防性強制</span><span class="sxs-lookup"><span data-stu-id="dd97e-157">Preventative mandatory</span></span> | <span data-ttu-id="dd97e-158">7</span><span class="sxs-lookup"><span data-stu-id="dd97e-158">27</span></span> |
| <span data-ttu-id="dd97e-159">預防自由</span><span class="sxs-lookup"><span data-stu-id="dd97e-159">Preventative discretionary</span></span> | <span data-ttu-id="dd97e-160">9 </span><span class="sxs-lookup"><span data-stu-id="dd97e-160">9</span></span> |
| <span data-ttu-id="dd97e-161">偵探強制</span><span class="sxs-lookup"><span data-stu-id="dd97e-161">Detective mandatory</span></span> | <span data-ttu-id="dd97e-162">3 </span><span class="sxs-lookup"><span data-stu-id="dd97e-162">3</span></span> |
| <span data-ttu-id="dd97e-163">偵探自由</span><span class="sxs-lookup"><span data-stu-id="dd97e-163">Detective discretionary</span></span> | <span data-ttu-id="dd97e-164">1 </span><span class="sxs-lookup"><span data-stu-id="dd97e-164">1</span></span> |
| <span data-ttu-id="dd97e-165">必要修正</span><span class="sxs-lookup"><span data-stu-id="dd97e-165">Corrective mandatory</span></span> | <span data-ttu-id="dd97e-166">3 </span><span class="sxs-lookup"><span data-stu-id="dd97e-166">3</span></span> |
| <span data-ttu-id="dd97e-167">隨機糾正</span><span class="sxs-lookup"><span data-stu-id="dd97e-167">Corrective discretionary</span></span> | <span data-ttu-id="dd97e-168">1 </span><span class="sxs-lookup"><span data-stu-id="dd97e-168">1</span></span> |
  
<span data-ttu-id="dd97e-169">![合規性分數控制點值](../media/compliance-score-controls-scoring.png "合規性分數控制點值")</span><span class="sxs-lookup"><span data-stu-id="dd97e-169">![Compliance Score controls point values](../media/compliance-score-controls-scoring.png "Compliance Score controls point values")</span></span>