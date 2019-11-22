---
title: 合規性分數計算
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
description: 了解 Microsoft 合規性分數會根據 [地址風險採取的動作的個人化的分數的計算，並改善您的合規性狀態。
ms.openlocfilehash: a94b1051af383041a89fa136ae490875ea48782d
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793657"
---
# <a name="microsoft-compliance-score-preview-calculation"></a><span data-ttu-id="d7b2c-103">Microsoft 合規性分數 （預覽） 計算</span><span class="sxs-lookup"><span data-stu-id="d7b2c-103">Microsoft Compliance Score (Preview) calculation</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7b2c-104">合規性分數不 express 與任何特定的標準或法規的組織符合性絕對量值。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-104">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="d7b2c-105">它來表示您要採用的個人資料和個人隱私權降低風險的控制項的程度。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-105">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="d7b2c-106">合規性分數和合規性管理員中的建議事項不應該解譯成保證郵件可以合規性。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-106">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="d7b2c-107">這項服務目前處於預覽狀態，並受限於條款和條件[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-107">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="overview"></a><span data-ttu-id="d7b2c-108">概觀</span><span class="sxs-lookup"><span data-stu-id="d7b2c-108">Overview</span></span>

<span data-ttu-id="d7b2c-109">合規性分數儀表板會顯示措施的完成控制項內的改進動作進度的分數。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="d7b2c-110">您點累當您完成動作。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-110">Your points accrue when you complete actions.</span></span>

<span data-ttu-id="d7b2c-111">您的分數是根據 Microsoft 受管理的動作和客戶管理動作完成計算。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-111">Your score is calculated based on the completion of Microsoft-managed actions and customer-managed actions.</span></span> <span data-ttu-id="d7b2c-112">每個巨集指令具有不同的影響您分數，根據所涉及的潛在風險，因此分數有助於排列優先順序的巨集指令，將焦點放入改善您的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-112">Each action has a different impact on your score, depending on the potential risks involved, so the score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="d7b2c-113">控制項的顯示合規性分數的值會套用]*其完整*您通過/失敗為基礎的總分數。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-113">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="d7b2c-114">控制項實作並傳遞後續評估測試或沒有。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-114">Either the control is implemented and passes the subsequent assessment test or it does not.</span></span> <span data-ttu-id="d7b2c-115">當控制項有指派的點新增到合規性分數：</span><span class="sxs-lookup"><span data-stu-id="d7b2c-115">Assigned points are added to Compliance Score when the control has:</span></span>

- <span data-ttu-id="d7b2c-116">**實作狀態**等於**Implemented**或**替代實作**，</span><span class="sxs-lookup"><span data-stu-id="d7b2c-116">**Implementation Status** equals **Implemented** or **Alternative Implementation** and,</span></span>
- <span data-ttu-id="d7b2c-117">**測試結果**等於**Passed**。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-117">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="d7b2c-118">總和所採取的動作改進盈餘分析的資料點是控制項分數。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-118">The sum of points earned by taking improvement actions is the control score.</span></span> <span data-ttu-id="d7b2c-119">您控制分數的總和會評估分數。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-119">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="d7b2c-120">評估分數的總和，是整體合規性分數</span><span class="sxs-lookup"><span data-stu-id="d7b2c-120">The sum of your assessment scores is your overall compliance score</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="d7b2c-121">根據 Microsoft 365 的資料保護基準的初始分數</span><span class="sxs-lookup"><span data-stu-id="d7b2c-121">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="d7b2c-122">合規性分數可讓您根據 Microsoft 365 的資料保護基準，這是一組控制項包含重要的法規及標準的資料保護和一般資料控管的方塊出分數。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-122">Compliance Score gives you an out-of-the-box score based on the Microsoft 365 data protection baseline, which is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="d7b2c-123">此基準線繪製元素，主要是從 NIST CSF （National Institute of Standards 和技術 Cybersecurity Framework） 和 ISO （國際標準組織），以及從 FedRAMP （聯邦風險與授權管理程式） 和 GDPR （歐盟地區的一般資料保護規定）。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-123">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="d7b2c-124">如何合規性分數持續評估控制項</span><span class="sxs-lookup"><span data-stu-id="d7b2c-124">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="d7b2c-125">合規性分數自動透過 Microsoft 365 環境掃描，並會偵測到您系統的設定，連續且自動更新您的技術控制項狀態。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-125">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="d7b2c-126">例如，如果您開啟在 Azure AD 入口網站中的多重要素驗證 (MFA)，合規性分數偵測設定，並會反映在控制存取的解決方案詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-126">For example, if you turned on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="d7b2c-127">相反地，如果您未啟用 MFA，合規性分數的旗標，為您要採取的建議動作。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-127">Conversely, if you didn’t turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="d7b2c-128">合規性分數控制項狀態更新每隔 24 小時。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-128">Compliance Score updates your control status every 24 hours.</span></span> <span data-ttu-id="d7b2c-129">一旦您遵循建議實作控制項，您會看到控制項狀態更新的下一步] 一天。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-129">Once you follow a recommendation to implement a control, you will see the control status updated the next day.</span></span>

<span data-ttu-id="d7b2c-130">公開預覽期間連續評估是提供部分的控制項，但非全部。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-130">During public preview, continuous assessment is available to a portion controls, but not all.</span></span>
  
## <a name="control-types-and-points"></a><span data-ttu-id="d7b2c-131">控制項類型和點</span><span class="sxs-lookup"><span data-stu-id="d7b2c-131">Control types and points</span></span>

<span data-ttu-id="d7b2c-132">合規性分數追蹤兩種類型的控制項 — Microsoft 管理與客戶管理-每一種有參與您的整體分數的點：</span><span class="sxs-lookup"><span data-stu-id="d7b2c-132">Compliance Score tracks two types of controls—Microsoft-managed and customer-managed—each of which have points that contribute to your overall score:</span></span>

1. <span data-ttu-id="d7b2c-133">**客戶管理點**參與合規性分數根據貴組織所受管理的控制項。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-133">**Customer-managed points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="d7b2c-134">**Microsoft 受管理的點**參與您根據受管理的 microsoft 雲端服務提供者為控制項的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-134">**Microsoft-managed points** contribute to your compliance score based on controls managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="d7b2c-135">控制項會根據是否為強制或選擇性，以及他們是否已完成預防性、 偵查，或更正分數值指派給 — 如下所示。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-135">Controls are assigned a score value based on whether they are mandatory or discretionary, and whether they are preventative, detective, or corrective—as described below.</span></span>

### <a name="mandatory-and-discretionary-controls"></a><span data-ttu-id="d7b2c-136">必要和選擇性控制項</span><span class="sxs-lookup"><span data-stu-id="d7b2c-136">Mandatory and discretionary controls</span></span>

 - <span data-ttu-id="d7b2c-137">**必要的控制項**都是刻意或意外無法略過的動作。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-137">**Mandatory controls** are actions that cannot be bypassed either intentionally or accidentally.</span></span> <span data-ttu-id="d7b2c-138">例如，設定的密碼長度、 複雜性和到期需求集中管理密碼原則。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-138">An example is a centrally-managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="d7b2c-139">使用者必須符合這些需求，才能存取系統。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-139">Users must comply with these requirements to access the system.</span></span>
  
 - <span data-ttu-id="d7b2c-140">**選擇性控制**依賴使用者了解原則，並採取適當動作。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-140">**Discretionary controls** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="d7b2c-141">例如，要求他們離開時鎖定其電腦的使用者原則是選擇性的控制項，因為它必須依賴使用者。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-141">For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-controls"></a><span data-ttu-id="d7b2c-142">預防性、 偵測和修正的控制項</span><span class="sxs-lookup"><span data-stu-id="d7b2c-142">Preventative, detective, and corrective controls</span></span>
  
 - <span data-ttu-id="d7b2c-143">**完成預防性控制項**位址特定風險。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-143">**Preventative controls** address specific risks.</span></span> <span data-ttu-id="d7b2c-144">例如，保護使用加密的靜態的資訊是針對攻擊和外洩的預防性控制項。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-144">For example, protecting information at rest using encryption is a preventative control against attacks and breaches.</span></span> <span data-ttu-id="d7b2c-145">責任的區隔是管理衝突的利益與防範詐騙的預防性控制項。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-145">Separation of duties is a preventative control to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="d7b2c-146">**偵測控制項**主動監控系統以識別不規則條件或代表風險或，可用來偵測侵入或決定若發生外洩的行為。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-146">**Detective controls** actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach occurs.</span></span> <span data-ttu-id="d7b2c-147">系統存取稽核和特殊權限的系統管理動作稽核是偵測監視控制項的類型。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-147">System access auditing and privileged administrative actions auditing are types of detective monitoring controls.</span></span> <span data-ttu-id="d7b2c-148">法規遵循稽核是一種用來尋找程序問題的偵查控制項。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-148">Regulatory compliance audits are a type of detective control used to find process issues.</span></span>
  
- <span data-ttu-id="d7b2c-149">**更正控制項**嘗試保留不良影響的安全性事件最小值、 採取更正動作來降低立即生效，並盡可能反向所造成的損害。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-149">**Corrective controls** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="d7b2c-150">隱私權事件回應是更正控制項限制損害，並在外洩之後，還原至正常運作狀態的系統。</span><span class="sxs-lookup"><span data-stu-id="d7b2c-150">Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="d7b2c-151">每個控制項具有指派的值，根據其所代表之風險的合規性分數：</span><span class="sxs-lookup"><span data-stu-id="d7b2c-151">Each control has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="d7b2c-152">**類型**</span><span class="sxs-lookup"><span data-stu-id="d7b2c-152">**Type**</span></span>|<span data-ttu-id="d7b2c-153">**指派的分數**</span><span class="sxs-lookup"><span data-stu-id="d7b2c-153">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="d7b2c-154">必要的預防性</span><span class="sxs-lookup"><span data-stu-id="d7b2c-154">Preventative mandatory</span></span> | <span data-ttu-id="d7b2c-155">27</span><span class="sxs-lookup"><span data-stu-id="d7b2c-155">27</span></span> |
| <span data-ttu-id="d7b2c-156">選擇性的預防性</span><span class="sxs-lookup"><span data-stu-id="d7b2c-156">Preventative discretionary</span></span> | <span data-ttu-id="d7b2c-157">9 </span><span class="sxs-lookup"><span data-stu-id="d7b2c-157">9</span></span> |
| <span data-ttu-id="d7b2c-158">偵測必要</span><span class="sxs-lookup"><span data-stu-id="d7b2c-158">Detective mandatory</span></span> | <span data-ttu-id="d7b2c-159">3 </span><span class="sxs-lookup"><span data-stu-id="d7b2c-159">3</span></span> |
| <span data-ttu-id="d7b2c-160">偵測選擇性</span><span class="sxs-lookup"><span data-stu-id="d7b2c-160">Detective discretionary</span></span> | <span data-ttu-id="d7b2c-161">1 </span><span class="sxs-lookup"><span data-stu-id="d7b2c-161">1</span></span> |
| <span data-ttu-id="d7b2c-162">必要的矯正措施</span><span class="sxs-lookup"><span data-stu-id="d7b2c-162">Corrective mandatory</span></span> | <span data-ttu-id="d7b2c-163">3 </span><span class="sxs-lookup"><span data-stu-id="d7b2c-163">3</span></span> |
| <span data-ttu-id="d7b2c-164">修正了選擇性</span><span class="sxs-lookup"><span data-stu-id="d7b2c-164">Corrective discretionary</span></span> | <span data-ttu-id="d7b2c-165">1 </span><span class="sxs-lookup"><span data-stu-id="d7b2c-165">1</span></span> |
  