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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 232d19cb0bcb6a2f91c1bdad15d842ec7396499c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201048"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="cc327-104">Microsoft 威脅防護中的自動調查遵循的修復動作</span><span class="sxs-lookup"><span data-stu-id="cc327-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cc327-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cc327-105">**Applies to:**</span></span>
- <span data-ttu-id="cc327-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="cc327-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="cc327-107">補救動作</span><span class="sxs-lookup"><span data-stu-id="cc327-107">Remediation actions</span></span>

<span data-ttu-id="cc327-108">在 Microsoft 威脅防護中的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。</span><span class="sxs-lookup"><span data-stu-id="cc327-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="cc327-109">對裝置（也稱為端點）採取某些類型的修復動作。</span><span class="sxs-lookup"><span data-stu-id="cc327-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="cc327-110">對電子郵件內容採取其他修復動作。</span><span class="sxs-lookup"><span data-stu-id="cc327-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="cc327-111">在採取修正動作、核准或拒絕時，自動調查會完成。</span><span class="sxs-lookup"><span data-stu-id="cc327-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="cc327-112">下表摘要說明 Microsoft 威脅防護目前支援的修復動作：</span><span class="sxs-lookup"><span data-stu-id="cc327-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="cc327-113">裝置 (端點) 修正動作</span><span class="sxs-lookup"><span data-stu-id="cc327-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="cc327-114">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="cc327-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="cc327-115">-收集調查套件</span><span class="sxs-lookup"><span data-stu-id="cc327-115">- Collect investigation package</span></span> <br/><span data-ttu-id="cc327-116">-隔離裝置 (此動作可復原) </span><span class="sxs-lookup"><span data-stu-id="cc327-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="cc327-117">-下架電腦</span><span class="sxs-lookup"><span data-stu-id="cc327-117">- Offboard machine</span></span> <br/><span data-ttu-id="cc327-118">-發行程式碼執行</span><span class="sxs-lookup"><span data-stu-id="cc327-118">- Release code execution</span></span> <br/><span data-ttu-id="cc327-119">-從隔離區發行</span><span class="sxs-lookup"><span data-stu-id="cc327-119">- Release from quarantine</span></span> <br/><span data-ttu-id="cc327-120">-要求範例</span><span class="sxs-lookup"><span data-stu-id="cc327-120">- Request sample</span></span> <br/><span data-ttu-id="cc327-121">-限制執行程式碼執行 (此巨集指令可復原) </span><span class="sxs-lookup"><span data-stu-id="cc327-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="cc327-122">-執行防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="cc327-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="cc327-123">-停止和隔離</span><span class="sxs-lookup"><span data-stu-id="cc327-123">- Stop and quarantine</span></span>      |<span data-ttu-id="cc327-124">-)  (時，封鎖 URL</span><span class="sxs-lookup"><span data-stu-id="cc327-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="cc327-125">-虛刪除電子郵件訊息或聚簇</span><span class="sxs-lookup"><span data-stu-id="cc327-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="cc327-126">-隔離電子郵件</span><span class="sxs-lookup"><span data-stu-id="cc327-126">- Quarantine email</span></span><br/><span data-ttu-id="cc327-127">-隔離電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="cc327-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="cc327-128">-關閉外部郵件轉發</span><span class="sxs-lookup"><span data-stu-id="cc327-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="cc327-129">您可以在「 [行動中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)」查看修正動作（不論是待核准或已完成）。</span><span class="sxs-lookup"><span data-stu-id="cc327-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="cc327-130">修正動作遵循自動調查</span><span class="sxs-lookup"><span data-stu-id="cc327-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="cc327-131">當自動調查完成時，所涉及的每一項證據都會達到序判定。</span><span class="sxs-lookup"><span data-stu-id="cc327-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="cc327-132">根據判定，修正動作的識別。</span><span class="sxs-lookup"><span data-stu-id="cc327-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="cc327-133">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="cc327-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="cc327-134">這完全取決於如何 [設定自動調查和回應](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="cc327-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="cc327-135">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="cc327-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="cc327-136">裁決</span><span class="sxs-lookup"><span data-stu-id="cc327-136">Verdict</span></span>    |<span data-ttu-id="cc327-137">範圍</span><span class="sxs-lookup"><span data-stu-id="cc327-137">Area</span></span>    |<span data-ttu-id="cc327-138">結果</span><span class="sxs-lookup"><span data-stu-id="cc327-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="cc327-139">惡意</span><span class="sxs-lookup"><span data-stu-id="cc327-139">Malicious</span></span>    |<span data-ttu-id="cc327-140">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="cc327-140">Devices (endpoints)</span></span>    |<span data-ttu-id="cc327-141">如果您組織的 [裝置群組](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) 會自動設定為 **完整修正威脅** ，便會自動採取修正動作 () </span><span class="sxs-lookup"><span data-stu-id="cc327-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="cc327-142">惡意</span><span class="sxs-lookup"><span data-stu-id="cc327-142">Malicious</span></span>    |<span data-ttu-id="cc327-143">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="cc327-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="cc327-144">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="cc327-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="cc327-145">可疑</span><span class="sxs-lookup"><span data-stu-id="cc327-145">Suspicious</span></span>    |<span data-ttu-id="cc327-146">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="cc327-146">Devices or email content</span></span> |<span data-ttu-id="cc327-147">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="cc327-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="cc327-148">找不到威脅</span><span class="sxs-lookup"><span data-stu-id="cc327-148">No threats found</span></span>    |<span data-ttu-id="cc327-149">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="cc327-149">Devices or email content</span></span>    |<span data-ttu-id="cc327-150">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="cc327-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="cc327-151">是否自動採取修復動作，也取決於特定設定，例如組織的裝置群組原則。</span><span class="sxs-lookup"><span data-stu-id="cc327-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="cc327-152">若要深入瞭解，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="cc327-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="cc327-153">在 Microsoft 威脅防護中設定自動化調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="cc327-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="cc327-154">如何在裝置上修正威脅</span><span class="sxs-lookup"><span data-stu-id="cc327-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="cc327-155">後續步驟</span><span class="sxs-lookup"><span data-stu-id="cc327-155">Next steps</span></span>

- [<span data-ttu-id="cc327-156">造訪重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="cc327-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="cc327-157">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="cc327-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="cc327-158">在自動化調查和回應功能中處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="cc327-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
