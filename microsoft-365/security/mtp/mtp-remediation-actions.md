---
title: 下列 Microsoft 威脅防護中的自動化的調查的修復動作
description: 取得遵循 Microsoft 威脅防護中的自動化的調查的補救動作的概觀
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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266049"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="22bdb-104">下列 Microsoft 威脅防護中的自動化的調查的修復動作</span><span class="sxs-lookup"><span data-stu-id="22bdb-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="22bdb-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="22bdb-105">**Applies to:**</span></span>
- <span data-ttu-id="22bdb-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="22bdb-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="22bdb-107">補救動作</span><span class="sxs-lookup"><span data-stu-id="22bdb-107">Remediation actions</span></span>

<span data-ttu-id="22bdb-108">期間和之後自動進行調查，Microsoft 威脅防護中，修復動作會被識別為惡意或可疑的項目。</span><span class="sxs-lookup"><span data-stu-id="22bdb-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="22bdb-109">某些類型的補救動作所採取的裝置，也稱為端點。</span><span class="sxs-lookup"><span data-stu-id="22bdb-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="22bdb-110">在 [電子郵件內容上採取其他修復動作。</span><span class="sxs-lookup"><span data-stu-id="22bdb-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="22bdb-111">自動化調查完成後採取、 核准或拒絕修復動作。</span><span class="sxs-lookup"><span data-stu-id="22bdb-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="22bdb-112">下表摘要說明目前支援 Microsoft 威脅防護中的補救動作：</span><span class="sxs-lookup"><span data-stu-id="22bdb-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="22bdb-113">裝置 （端點） 修復動作</span><span class="sxs-lookup"><span data-stu-id="22bdb-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="22bdb-114">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="22bdb-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="22bdb-115">隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="22bdb-115">Quarantine file</span></span><br/><span data-ttu-id="22bdb-116">移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="22bdb-116">Remove registry key</span></span><br/><span data-ttu-id="22bdb-117">刪除處理序</span><span class="sxs-lookup"><span data-stu-id="22bdb-117">Kill process</span></span> <br/><span data-ttu-id="22bdb-118">停止服務</span><span class="sxs-lookup"><span data-stu-id="22bdb-118">Stop service</span></span> <br/><span data-ttu-id="22bdb-119">停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="22bdb-119">Disable driver</span></span> <br/><span data-ttu-id="22bdb-120">移除排程工作</span><span class="sxs-lookup"><span data-stu-id="22bdb-120">Remove scheduled task</span></span>      |<span data-ttu-id="22bdb-121">虛刪除電子郵件訊息或群集</span><span class="sxs-lookup"><span data-stu-id="22bdb-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="22bdb-122">封鎖 URL (點擊時)</span><span class="sxs-lookup"><span data-stu-id="22bdb-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="22bdb-123">關閉外部郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="22bdb-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="22bdb-124">修復動作，不論他們正在等待核准或已完成，可以檢視在[重要訊息中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)。</span><span class="sxs-lookup"><span data-stu-id="22bdb-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="22bdb-125">結果和下列自動化的調查的結果</span><span class="sxs-lookup"><span data-stu-id="22bdb-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="22bdb-126">當自動調查完成後，會對所涉及的每個證據做出裁決，並確定修正動作。</span><span class="sxs-lookup"><span data-stu-id="22bdb-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="22bdb-127">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="22bdb-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="22bdb-128">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="22bdb-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="22bdb-129">裁決</span><span class="sxs-lookup"><span data-stu-id="22bdb-129">Verdict</span></span>    |<span data-ttu-id="22bdb-130">範圍</span><span class="sxs-lookup"><span data-stu-id="22bdb-130">Area</span></span>   |<span data-ttu-id="22bdb-131">結果</span><span class="sxs-lookup"><span data-stu-id="22bdb-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="22bdb-132">惡意</span><span class="sxs-lookup"><span data-stu-id="22bdb-132">Malicious</span></span>  |<span data-ttu-id="22bdb-133">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="22bdb-133">Devices (endpoints)</span></span>    |<span data-ttu-id="22bdb-134">自動採取修正動作</span><span class="sxs-lookup"><span data-stu-id="22bdb-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="22bdb-135">惡意</span><span class="sxs-lookup"><span data-stu-id="22bdb-135">Malicious</span></span>  |<span data-ttu-id="22bdb-136">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="22bdb-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="22bdb-137">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="22bdb-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="22bdb-138">可疑</span><span class="sxs-lookup"><span data-stu-id="22bdb-138">Suspicious</span></span> |<span data-ttu-id="22bdb-139">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="22bdb-139">Devices or email content</span></span> |<span data-ttu-id="22bdb-140">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="22bdb-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="22bdb-141">無害</span><span class="sxs-lookup"><span data-stu-id="22bdb-141">Clean</span></span>  |<span data-ttu-id="22bdb-142">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="22bdb-142">Devices or email content</span></span>   |<span data-ttu-id="22bdb-143">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="22bdb-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="22bdb-144">在控制中心檢閱待核准的動作</span><span class="sxs-lookup"><span data-stu-id="22bdb-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="22bdb-145">如果您認為某個項目已未接或錯誤偵測到的自動化的調查和 Microsoft 威脅防護中的回應功能，讓我們知道 ！</span><span class="sxs-lookup"><span data-stu-id="22bdb-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="22bdb-146">[報表 positive/誤判](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="22bdb-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="22bdb-147">後續步驟</span><span class="sxs-lookup"><span data-stu-id="22bdb-147">Next steps</span></span>

- [<span data-ttu-id="22bdb-148">核准或拒絕動作</span><span class="sxs-lookup"><span data-stu-id="22bdb-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="22bdb-149">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="22bdb-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
