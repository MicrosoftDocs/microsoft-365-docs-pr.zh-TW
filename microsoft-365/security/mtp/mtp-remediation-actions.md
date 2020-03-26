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
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955588"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="aa40b-104">Microsoft 威脅防護中的自動調查遵循的修復動作</span><span class="sxs-lookup"><span data-stu-id="aa40b-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="aa40b-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="aa40b-105">**Applies to:**</span></span>
- <span data-ttu-id="aa40b-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="aa40b-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="aa40b-107">補救動作</span><span class="sxs-lookup"><span data-stu-id="aa40b-107">Remediation actions</span></span>

<span data-ttu-id="aa40b-108">在 Microsoft 威脅防護中的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。</span><span class="sxs-lookup"><span data-stu-id="aa40b-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="aa40b-109">對裝置（也稱為端點）採取某些類型的修復動作。</span><span class="sxs-lookup"><span data-stu-id="aa40b-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="aa40b-110">對電子郵件內容採取其他修復動作。</span><span class="sxs-lookup"><span data-stu-id="aa40b-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="aa40b-111">在採取修正動作、核准或拒絕時，自動調查會完成。</span><span class="sxs-lookup"><span data-stu-id="aa40b-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="aa40b-112">下表摘要說明 Microsoft 威脅防護目前支援的修復動作：</span><span class="sxs-lookup"><span data-stu-id="aa40b-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="aa40b-113">裝置（端點）修復動作</span><span class="sxs-lookup"><span data-stu-id="aa40b-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="aa40b-114">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="aa40b-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="aa40b-115">隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="aa40b-115">Quarantine file</span></span><br/><span data-ttu-id="aa40b-116">移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="aa40b-116">Remove registry key</span></span><br/><span data-ttu-id="aa40b-117">刪除處理序</span><span class="sxs-lookup"><span data-stu-id="aa40b-117">Kill process</span></span> <br/><span data-ttu-id="aa40b-118">停止服務</span><span class="sxs-lookup"><span data-stu-id="aa40b-118">Stop service</span></span> <br/><span data-ttu-id="aa40b-119">停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="aa40b-119">Disable driver</span></span> <br/><span data-ttu-id="aa40b-120">移除排程工作</span><span class="sxs-lookup"><span data-stu-id="aa40b-120">Remove scheduled task</span></span>      |<span data-ttu-id="aa40b-121">虛刪除電子郵件訊息或群集</span><span class="sxs-lookup"><span data-stu-id="aa40b-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="aa40b-122">封鎖 URL (點擊時)</span><span class="sxs-lookup"><span data-stu-id="aa40b-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="aa40b-123">關閉外部郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="aa40b-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="aa40b-124">修正動作（不論是待核准或已完成），都可以在「[行動中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)」中查看。</span><span class="sxs-lookup"><span data-stu-id="aa40b-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="aa40b-125">修正動作遵循自動調查</span><span class="sxs-lookup"><span data-stu-id="aa40b-125">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="aa40b-126">當自動調查完成後，會對所涉及的每個證據做出裁決，並確定修正動作。</span><span class="sxs-lookup"><span data-stu-id="aa40b-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="aa40b-127">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="aa40b-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="aa40b-128">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="aa40b-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="aa40b-129">裁決</span><span class="sxs-lookup"><span data-stu-id="aa40b-129">Verdict</span></span>    |<span data-ttu-id="aa40b-130">範圍</span><span class="sxs-lookup"><span data-stu-id="aa40b-130">Area</span></span>    |<span data-ttu-id="aa40b-131">結果</span><span class="sxs-lookup"><span data-stu-id="aa40b-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="aa40b-132">惡意</span><span class="sxs-lookup"><span data-stu-id="aa40b-132">Malicious</span></span>    |<span data-ttu-id="aa40b-133">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="aa40b-133">Devices (endpoints)</span></span>    |<span data-ttu-id="aa40b-134">自動採取修正動作</span><span class="sxs-lookup"><span data-stu-id="aa40b-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="aa40b-135">惡意</span><span class="sxs-lookup"><span data-stu-id="aa40b-135">Malicious</span></span>    |<span data-ttu-id="aa40b-136">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="aa40b-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="aa40b-137">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="aa40b-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="aa40b-138">可疑</span><span class="sxs-lookup"><span data-stu-id="aa40b-138">Suspicious</span></span>    |<span data-ttu-id="aa40b-139">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="aa40b-139">Devices or email content</span></span> |<span data-ttu-id="aa40b-140">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="aa40b-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="aa40b-141">找不到威脅</span><span class="sxs-lookup"><span data-stu-id="aa40b-141">No threats found</span></span>    |<span data-ttu-id="aa40b-142">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="aa40b-142">Devices or email content</span></span>    |<span data-ttu-id="aa40b-143">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="aa40b-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="aa40b-144">在控制中心檢閱待核准的動作</span><span class="sxs-lookup"><span data-stu-id="aa40b-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="aa40b-145">如果您認為 Microsoft 威脅防護中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請告訴我們！</span><span class="sxs-lookup"><span data-stu-id="aa40b-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="aa40b-146">[報告誤報/負片](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="aa40b-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="aa40b-147">後續步驟</span><span class="sxs-lookup"><span data-stu-id="aa40b-147">Next steps</span></span>

- [<span data-ttu-id="aa40b-148">核准或拒絕動作</span><span class="sxs-lookup"><span data-stu-id="aa40b-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="aa40b-149">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="aa40b-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
