---
title: Microsoft 威脅防護中的自動調查遵循的修復動作
description: 深入瞭解在 Microsoft 威脅防護中遵循自動調查的修復動作
keywords: automated, investigation, alert, trigger, action, remediation, 自動化, 調查, 警示, 觸發, 動作, 補救
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502934"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="bf9b9-104">Microsoft 威脅防護中的自動調查遵循的修復動作</span><span class="sxs-lookup"><span data-stu-id="bf9b9-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="bf9b9-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf9b9-105">**Applies to:**</span></span>
- <span data-ttu-id="bf9b9-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bf9b9-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="bf9b9-107">補救動作</span><span class="sxs-lookup"><span data-stu-id="bf9b9-107">Remediation actions</span></span>

<span data-ttu-id="bf9b9-108">在 Microsoft 威脅防護中的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。</span><span class="sxs-lookup"><span data-stu-id="bf9b9-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="bf9b9-109">對裝置（也稱為端點）採取某些類型的修復動作。</span><span class="sxs-lookup"><span data-stu-id="bf9b9-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="bf9b9-110">對電子郵件內容採取其他修復動作。</span><span class="sxs-lookup"><span data-stu-id="bf9b9-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="bf9b9-111">在採取修正動作、核准或拒絕時，自動調查會完成。</span><span class="sxs-lookup"><span data-stu-id="bf9b9-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="bf9b9-112">下表摘要說明 Microsoft 威脅防護目前支援的修復動作：</span><span class="sxs-lookup"><span data-stu-id="bf9b9-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="bf9b9-113">裝置（端點）修復動作</span><span class="sxs-lookup"><span data-stu-id="bf9b9-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="bf9b9-114">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="bf9b9-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="bf9b9-115">-收集調查套件</span><span class="sxs-lookup"><span data-stu-id="bf9b9-115">- Collect investigation package</span></span> <br/><span data-ttu-id="bf9b9-116">隔離裝置（可以復原此動作）</span><span class="sxs-lookup"><span data-stu-id="bf9b9-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="bf9b9-117">-下架電腦</span><span class="sxs-lookup"><span data-stu-id="bf9b9-117">- Offboard machine</span></span> <br/><span data-ttu-id="bf9b9-118">-發行程式碼執行</span><span class="sxs-lookup"><span data-stu-id="bf9b9-118">- Release code execution</span></span> <br/><span data-ttu-id="bf9b9-119">-從隔離區發行</span><span class="sxs-lookup"><span data-stu-id="bf9b9-119">- Release from quarantine</span></span> <br/><span data-ttu-id="bf9b9-120">-要求範例</span><span class="sxs-lookup"><span data-stu-id="bf9b9-120">- Request sample</span></span> <br/><span data-ttu-id="bf9b9-121">-限制執行程式碼（可以復原此動作）</span><span class="sxs-lookup"><span data-stu-id="bf9b9-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="bf9b9-122">-執行防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="bf9b9-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="bf9b9-123">-停止和隔離</span><span class="sxs-lookup"><span data-stu-id="bf9b9-123">- Stop and quarantine</span></span>      |<span data-ttu-id="bf9b9-124">-封鎖 URL （按一下時間）</span><span class="sxs-lookup"><span data-stu-id="bf9b9-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="bf9b9-125">-虛刪除電子郵件訊息或聚簇</span><span class="sxs-lookup"><span data-stu-id="bf9b9-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="bf9b9-126">-隔離電子郵件</span><span class="sxs-lookup"><span data-stu-id="bf9b9-126">- Quarantine email</span></span><br/><span data-ttu-id="bf9b9-127">-隔離電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="bf9b9-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="bf9b9-128">-關閉外部郵件轉發</span><span class="sxs-lookup"><span data-stu-id="bf9b9-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="bf9b9-129">修正動作（不論是待核准或已完成），都可以在「[行動中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)」中查看。</span><span class="sxs-lookup"><span data-stu-id="bf9b9-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="bf9b9-130">修正動作遵循自動調查</span><span class="sxs-lookup"><span data-stu-id="bf9b9-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="bf9b9-131">當自動調查完成後，會對所涉及的每個證據做出裁決，並確定修正動作。</span><span class="sxs-lookup"><span data-stu-id="bf9b9-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="bf9b9-132">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="bf9b9-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="bf9b9-133">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="bf9b9-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="bf9b9-134">裁決</span><span class="sxs-lookup"><span data-stu-id="bf9b9-134">Verdict</span></span>    |<span data-ttu-id="bf9b9-135">範圍</span><span class="sxs-lookup"><span data-stu-id="bf9b9-135">Area</span></span>    |<span data-ttu-id="bf9b9-136">結果</span><span class="sxs-lookup"><span data-stu-id="bf9b9-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="bf9b9-137">惡意</span><span class="sxs-lookup"><span data-stu-id="bf9b9-137">Malicious</span></span>    |<span data-ttu-id="bf9b9-138">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="bf9b9-138">Devices (endpoints)</span></span>    |<span data-ttu-id="bf9b9-139">自動採取修正動作</span><span class="sxs-lookup"><span data-stu-id="bf9b9-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="bf9b9-140">惡意</span><span class="sxs-lookup"><span data-stu-id="bf9b9-140">Malicious</span></span>    |<span data-ttu-id="bf9b9-141">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="bf9b9-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="bf9b9-142">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="bf9b9-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="bf9b9-143">可疑</span><span class="sxs-lookup"><span data-stu-id="bf9b9-143">Suspicious</span></span>    |<span data-ttu-id="bf9b9-144">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="bf9b9-144">Devices or email content</span></span> |<span data-ttu-id="bf9b9-145">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="bf9b9-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="bf9b9-146">找不到威脅</span><span class="sxs-lookup"><span data-stu-id="bf9b9-146">No threats found</span></span>    |<span data-ttu-id="bf9b9-147">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="bf9b9-147">Devices or email content</span></span>    |<span data-ttu-id="bf9b9-148">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="bf9b9-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="bf9b9-149">在控制中心檢閱待核准的動作</span><span class="sxs-lookup"><span data-stu-id="bf9b9-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="bf9b9-150">如果您認為 Microsoft 威脅防護中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請告訴我們！</span><span class="sxs-lookup"><span data-stu-id="bf9b9-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="bf9b9-151">[報告誤報/負片](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9b9-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf9b9-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="bf9b9-152">Next steps</span></span>

- [<span data-ttu-id="bf9b9-153">核准或拒絕動作</span><span class="sxs-lookup"><span data-stu-id="bf9b9-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="bf9b9-154">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="bf9b9-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
