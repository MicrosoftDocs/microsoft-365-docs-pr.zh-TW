---
title: 合規性分數方法
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
description: Microsoft Compliance Manager 是在 Microsoft 服務信任入口網站中的可用工作流程為基礎的風險評估工具。 合規性管理員可讓您追蹤、 指派及驗證與 Microsoft 雲端服務相關的法規合規性活動。
ms.openlocfilehash: 148920fac825dab9f67a79bc11907b72218e47bc
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076627"
---
# <a name="compliance-score-methodology-preview"></a><span data-ttu-id="4fdb8-104">合規性分數方法 （預覽）</span><span class="sxs-lookup"><span data-stu-id="4fdb8-104">Compliance Score Methodology (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="4fdb8-p102">合規性分數並不會表達組織符合任何特定標準或規定的絕對測量。而是表示您採用控制項的程度，可降低個人資料和個別隱私權的風險。沒有任何服務可保證您符合標準或規定，且不能以任何形式解釋合規性分數作為保證。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-p102">The Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation. It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy. No service can guarantee that you are compliant with a standard or regulation, and the Compliance Score should not be interpreted as a guarantee in any way.</span></span>

<span data-ttu-id="4fdb8-108">合規性管理員儀表板會顯示針對評估每個評估磚合規性總分。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-108">The Compliance Manager dashboard displays a total compliance score for Assessments in each Assessment tile.</span></span> <span data-ttu-id="4fdb8-109">這是整體合規性分數評估，而且累積的評估中每個已實作和測試控制項接收到的點。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-109">This is the overall Compliance Score for the Assessment and is the accumulation of points received for each implemented and tested control in the Assessment.</span></span> <span data-ttu-id="4fdb8-110">針對新的 「 評估，合規性分數會具有由獨立第三方測試包含 Microsoft 管理控制項的初始值。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-110">For a new Assessment, the Compliance Score has an initial value for the included Microsoft-managed controls tested by independent third parties.</span></span> <span data-ttu-id="4fdb8-111">合規性分數可協助排列優先順序的評估和控制項以專注於改善您的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-111">Compliance Score can help prioritize which Assessments and controls to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="4fdb8-112">控制項的顯示合規性分數的值會套用]*其完整*總合規性分數以通過/失敗為基礎。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-112">The displayed Compliance Score values for the control are applied *in their entirety* to the total Compliance Score on a pass/fail basis.</span></span> <span data-ttu-id="4fdb8-113">控制項實作並傳遞後續評估測試或沒有。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-113">Either the control is implemented and passes the subsequent assessment test or it does not.</span></span> <span data-ttu-id="4fdb8-114">沒有部分實作任何部分信用卡。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-114">There is no partial credit for a partial implementation.</span></span> <span data-ttu-id="4fdb8-115">當控制項有指派的點新增到合規性分數：</span><span class="sxs-lookup"><span data-stu-id="4fdb8-115">Assigned points are added to the Compliance Score when the Control has:</span></span>

- <span data-ttu-id="4fdb8-116">**實作狀態**等於**Implemented**或**替代實作**，</span><span class="sxs-lookup"><span data-stu-id="4fdb8-116">**Implementation Status** equals **Implemented** or **Alternative Implementation** and,</span></span>
- <span data-ttu-id="4fdb8-117">**測試結果**等於**Passed**。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-117">**Test Result** equals **Passed**.</span></span>

## <a name="compliance-score"></a><span data-ttu-id="4fdb8-118">合規性分數</span><span class="sxs-lookup"><span data-stu-id="4fdb8-118">Compliance score</span></span>
  
<span data-ttu-id="4fdb8-119">在合規性管理員中，基準分數會將從 「 控制層級的動作項目層級。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-119">In Compliance Manager, baseline scores move from the Control level to the Action Item level.</span></span> <span data-ttu-id="4fdb8-120">分數會根據用途 （偵測、 預防性或矯正措施） 和強制執行 （選擇性或強制） 的動作項目。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-120">Scores are based on the purpose (Detective, Preventative, or Corrective) and enforcement (Discretionary or Mandatory) of the Action Item.</span></span>

<span data-ttu-id="4fdb8-121">動作項目會對應至控制項，且當控制項對應至多個動作項目，這些動作項目分數的總和控制項分數。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-121">Action Items are mapped to Controls, and when a Control is mapped to multiple Action Items, the sum of the Action Item Scores is the Control Score.</span></span> <span data-ttu-id="4fdb8-122">所有的控制項中的特定評估控制項分數的總和會評估分數。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-122">The sum of the Control Score for all Controls in a given Assessment is the Assessment Score.</span></span> <span data-ttu-id="4fdb8-123">在群組中的所有評估的平均分數是該群組合規性分數。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-123">The average score of all Assessments in a Group is the Compliance Score for that group.</span></span>
  
### <a name="mandatory-or-discretionary-controls"></a><span data-ttu-id="4fdb8-124">必要或選擇性控制項</span><span class="sxs-lookup"><span data-stu-id="4fdb8-124">Mandatory or discretionary Controls</span></span>
  
 <span data-ttu-id="4fdb8-125">**必要的控制項**都是刻意或意外無法略過的動作。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-125">**Mandatory Controls** are actions that cannot be bypassed either intentionally or accidentally.</span></span> <span data-ttu-id="4fdb8-126">常見的必要控制項的範例是集中管理的密碼原則設定的密碼長度、 複雜性和到期需求。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-126">An example of a common mandatory control is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="4fdb8-127">使用者必須符合這些需求，才能存取系統。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-127">Users must comply with these requirements to access the system.</span></span>
  
 <span data-ttu-id="4fdb8-128">**判別控制項**依賴使用者了解原則，並採取適當動作。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-128">**Discretionary Controls** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="4fdb8-129">例如，要求他們離開時鎖定其電腦的使用者原則是選擇性的控制項，因為它必須依賴使用者。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-129">For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user.</span></span>
  
### <a name="preventative-detective-or-corrective-controls"></a><span data-ttu-id="4fdb8-130">預防性、 偵測性或修正控制項</span><span class="sxs-lookup"><span data-stu-id="4fdb8-130">Preventative, detective, or corrective Controls</span></span>
  
 <span data-ttu-id="4fdb8-131">**預防性控制項**是防止特定的風險的動作。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-131">**Preventative Controls** are actions that prevent specific risks.</span></span> <span data-ttu-id="4fdb8-132">例如，保護使用加密的靜態的資訊是不受攻擊外, 洩的預防性控制項。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-132">For example, protecting information at rest using encryption is a preventative control against attacks, breaches.</span></span> <span data-ttu-id="4fdb8-133">責任的區隔是以管理衝突的感興趣，並防止詐騙的預防性控制項。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-133">Separation of duties is a preventative control to manage conflict of interest and to guard against fraud.</span></span>
  
 <span data-ttu-id="4fdb8-134">**偵測控制項**是主動監控系統以識別不規則條件或行為代表風險或，可用來偵測侵入或判斷是否有發生資料外洩的動作。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-134">**Detective Controls** are actions that actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach has occurred.</span></span> <span data-ttu-id="4fdb8-135">系統存取稽核和特殊權限的系統管理動作稽核是偵測監視控制項的類型。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-135">System access auditing and privileged administrative actions auditing are types of detective monitoring controls.</span></span> <span data-ttu-id="4fdb8-136">法規遵循稽核是一種用來尋找程序問題的偵查控制項。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-136">Regulatory compliance audits are a type of detective control used to find process issues.</span></span>
  
<span data-ttu-id="4fdb8-137">**更正控制項**是嘗試保留不良影響的安全性事件最小值、 採取更正動作來降低立即生效，並盡可能反向損毀的控制項。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-137">**Corrective Controls** are Controls that try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage, if possible.</span></span> <span data-ttu-id="4fdb8-138">隱私權事件回應是更正控制項限制損害，並在外洩之後，還原至正常運作狀態的系統。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-138">Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="4fdb8-139">每個控制項具有指派的值在合規性管理員根據其所代表之風險：</span><span class="sxs-lookup"><span data-stu-id="4fdb8-139">Each Control has an assigned value in Compliance Manager based on the risk that it represents:</span></span>

|<span data-ttu-id="4fdb8-140">**Type**</span><span class="sxs-lookup"><span data-stu-id="4fdb8-140">**Type**</span></span>|<span data-ttu-id="4fdb8-141">**指派的分數**</span><span class="sxs-lookup"><span data-stu-id="4fdb8-141">**Assigned Score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="4fdb8-142">完成預防性強制</span><span class="sxs-lookup"><span data-stu-id="4fdb8-142">Preventative Mandatory</span></span> | <span data-ttu-id="4fdb8-143">27</span><span class="sxs-lookup"><span data-stu-id="4fdb8-143">27</span></span> |
| <span data-ttu-id="4fdb8-144">選擇性的預防性</span><span class="sxs-lookup"><span data-stu-id="4fdb8-144">Preventative Discretionary</span></span> | <span data-ttu-id="4fdb8-145">9 </span><span class="sxs-lookup"><span data-stu-id="4fdb8-145">9</span></span> |
| <span data-ttu-id="4fdb8-146">偵查強制</span><span class="sxs-lookup"><span data-stu-id="4fdb8-146">Detective Mandatory</span></span> | <span data-ttu-id="4fdb8-147">3</span><span class="sxs-lookup"><span data-stu-id="4fdb8-147">3</span></span> |
| <span data-ttu-id="4fdb8-148">偵測選擇性</span><span class="sxs-lookup"><span data-stu-id="4fdb8-148">Detective Discretionary</span></span> | <span data-ttu-id="4fdb8-149">1</span><span class="sxs-lookup"><span data-stu-id="4fdb8-149">1</span></span> |
| <span data-ttu-id="4fdb8-150">更正強制</span><span class="sxs-lookup"><span data-stu-id="4fdb8-150">Corrective Mandatory</span></span> | <span data-ttu-id="4fdb8-151">3</span><span class="sxs-lookup"><span data-stu-id="4fdb8-151">3</span></span> |
| <span data-ttu-id="4fdb8-152">修正了選擇性</span><span class="sxs-lookup"><span data-stu-id="4fdb8-152">Corrective Discretionary</span></span> | <span data-ttu-id="4fdb8-153">1</span><span class="sxs-lookup"><span data-stu-id="4fdb8-153">1</span></span> |
  
## <a name="action-item-workflow"></a><span data-ttu-id="4fdb8-154">動作項目工作流程</span><span class="sxs-lookup"><span data-stu-id="4fdb8-154">Action Item workflow</span></span>

<span data-ttu-id="4fdb8-155">以下是一般的動作項目的基本工作流程：</span><span class="sxs-lookup"><span data-stu-id="4fdb8-155">Here's the basic workflow for a typical Action Item:</span></span>
  
1. <span data-ttu-id="4fdb8-156">合規性、 風險、 隱私權、 及/或組織的資料保護長將工作指派給實作控制組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-156">The Compliance, Risk, Privacy, and/or Data Protection Officer of an organization assigns a task to someone in the organization to implement a control.</span></span> <span data-ttu-id="4fdb8-157">該人員可能是：</span><span class="sxs-lookup"><span data-stu-id="4fdb8-157">That person could be:</span></span>

    - <span data-ttu-id="4fdb8-158">企業原則擁有者。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-158">A business policy owner.</span></span>
    - <span data-ttu-id="4fdb8-159">IT 實施者。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-159">An IT implementer.</span></span>
    - <span data-ttu-id="4fdb8-160">若要執行的工作與責任組織中另一個個人。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-160">Another individual in the organization with responsibility to perform the task.</span></span>

2. <span data-ttu-id="4fdb8-161">該個別執行實作控制項所需的工作、 上傳到合規性管理員中，實作的辨識項和標記實作動作項目繫結的控制項。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-161">That individual performs the tasks necessary to implement the control, uploads evidence of implementation into Compliance Manager, and marks the Control tied to the Action Item as implemented.</span></span> <span data-ttu-id="4fdb8-162">一旦完成這些工作，他們會指派給驗證評估者動作項目。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-162">Once these tasks are completed, they assign the Action Item to an Assessor for validation.</span></span>

    <span data-ttu-id="4fdb8-163">評估可以是：</span><span class="sxs-lookup"><span data-stu-id="4fdb8-163">Assessors can be:</span></span>

    - <span data-ttu-id="4fdb8-164">執行驗證的組織內的控制項的內部評估。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-164">Internal assessors that perform validation of controls within an organization.</span></span>
    - <span data-ttu-id="4fdb8-165">外部評估者檢查、 驗證及證實合規性，例如稽核 Microsoft 雲端服務的協力廠商獨立組織。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-165">External assessors that examine, verify, and certify compliance, such as the third-party independent organizations that audit Microsoft's cloud services.</span></span>

3. <span data-ttu-id="4fdb8-166">評估者會驗證控制項及檢查辨識項和標記所評估控制項和評估的結果。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-166">The Assessor validates the control and examines the evidence and marks the control as assessed and the results of the assessment.</span></span>

<span data-ttu-id="4fdb8-167">所有的控制項相關聯的評估會評估，一旦評估已完成。</span><span class="sxs-lookup"><span data-stu-id="4fdb8-167">Once all the Controls associated with an Assessment are assessed, the Assessment is complete.</span></span>