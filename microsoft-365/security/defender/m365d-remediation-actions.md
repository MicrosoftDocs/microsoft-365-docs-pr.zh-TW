---
title: Microsoft 365 Defender 中的修正動作
description: 深入瞭解 Microsoft 365 Defender 中的自動調查遵循的修復動作
keywords: automated, investigation, alert, trigger, action, remediation, 自動化, 調查, 警示, 觸發, 動作, 補救
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f025f23242c28f698e6f67755cc59d21c4463914
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782942"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="9c29c-104">Microsoft 365 Defender 中的修正動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9c29c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9c29c-105">**Applies to:**</span></span>
- <span data-ttu-id="9c29c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c29c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9c29c-107">在 Microsoft 365 Defender 的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。</span><span class="sxs-lookup"><span data-stu-id="9c29c-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="9c29c-108">對裝置（也稱為端點）採取某些類型的修復動作。</span><span class="sxs-lookup"><span data-stu-id="9c29c-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="9c29c-109">對電子郵件內容採取其他修復動作。</span><span class="sxs-lookup"><span data-stu-id="9c29c-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="9c29c-110">在採取修正動作、核准或拒絕時，自動調查會完成。</span><span class="sxs-lookup"><span data-stu-id="9c29c-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c29c-111">是否自動採取修復動作，也取決於特定設定，例如自動化程度。</span><span class="sxs-lookup"><span data-stu-id="9c29c-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="9c29c-112">若要深入瞭解，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="9c29c-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="9c29c-113">在 Microsoft 365 Defender 中設定自動化調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="9c29c-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="9c29c-114">如何在裝置上修正威脅</span><span class="sxs-lookup"><span data-stu-id="9c29c-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="9c29c-115">電子郵件 & 共同作業內容的威脅和修正動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="9c29c-116">下表摘要 Microsoft 365 Defender 中目前支援的修復動作。</span><span class="sxs-lookup"><span data-stu-id="9c29c-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="9c29c-117">裝置 (端點) 修正動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="9c29c-118">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="9c29c-119">-收集調查套件</span><span class="sxs-lookup"><span data-stu-id="9c29c-119">- Collect investigation package</span></span> <br/><span data-ttu-id="9c29c-120">-隔離裝置 (此動作可復原) </span><span class="sxs-lookup"><span data-stu-id="9c29c-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="9c29c-121">-下架電腦</span><span class="sxs-lookup"><span data-stu-id="9c29c-121">- Offboard machine</span></span> <br/><span data-ttu-id="9c29c-122">-發行程式碼執行</span><span class="sxs-lookup"><span data-stu-id="9c29c-122">- Release code execution</span></span> <br/><span data-ttu-id="9c29c-123">-從隔離區發行</span><span class="sxs-lookup"><span data-stu-id="9c29c-123">- Release from quarantine</span></span> <br/><span data-ttu-id="9c29c-124">-要求範例</span><span class="sxs-lookup"><span data-stu-id="9c29c-124">- Request sample</span></span> <br/><span data-ttu-id="9c29c-125">-限制執行程式碼執行 (此巨集指令可復原) </span><span class="sxs-lookup"><span data-stu-id="9c29c-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="9c29c-126">-執行防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="9c29c-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="9c29c-127">-停止和隔離</span><span class="sxs-lookup"><span data-stu-id="9c29c-127">- Stop and quarantine</span></span>      |<span data-ttu-id="9c29c-128">-)  (時，封鎖 URL</span><span class="sxs-lookup"><span data-stu-id="9c29c-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="9c29c-129">-虛刪除電子郵件訊息或聚簇</span><span class="sxs-lookup"><span data-stu-id="9c29c-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="9c29c-130">-隔離電子郵件</span><span class="sxs-lookup"><span data-stu-id="9c29c-130">- Quarantine email</span></span><br/><span data-ttu-id="9c29c-131">-隔離電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="9c29c-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="9c29c-132">-關閉外部郵件轉發</span><span class="sxs-lookup"><span data-stu-id="9c29c-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="9c29c-133">您可以在「 [行動中心](m365d-action-center.md)」查看修正動作（不論是待核准或已完成）。</span><span class="sxs-lookup"><span data-stu-id="9c29c-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="9c29c-134">遵循自動調查的修復動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="9c29c-135">當自動調查完成時，所涉及的每一項證據都會達到序判定。</span><span class="sxs-lookup"><span data-stu-id="9c29c-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="9c29c-136">根據判定，修正動作的識別。</span><span class="sxs-lookup"><span data-stu-id="9c29c-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="9c29c-137">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="9c29c-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="9c29c-138">這完全取決於如何 [設定自動調查和回應](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="9c29c-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="9c29c-139">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="9c29c-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="9c29c-140">裁決</span><span class="sxs-lookup"><span data-stu-id="9c29c-140">Verdict</span></span>    | <span data-ttu-id="9c29c-141">受影響實體</span><span class="sxs-lookup"><span data-stu-id="9c29c-141">Affected entities</span></span>    | <span data-ttu-id="9c29c-142">結果</span><span class="sxs-lookup"><span data-stu-id="9c29c-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="9c29c-143">惡意</span><span class="sxs-lookup"><span data-stu-id="9c29c-143">Malicious</span></span>    | <span data-ttu-id="9c29c-144">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="9c29c-144">Devices (endpoints)</span></span>    | <span data-ttu-id="9c29c-145">如果您組織的 [裝置群組](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) 會自動設定為 **完整修正威脅** ，便會自動採取修正動作 () </span><span class="sxs-lookup"><span data-stu-id="9c29c-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="9c29c-146">惡意</span><span class="sxs-lookup"><span data-stu-id="9c29c-146">Malicious</span></span>    | <span data-ttu-id="9c29c-147">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="9c29c-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="9c29c-148">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="9c29c-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="9c29c-149">可疑</span><span class="sxs-lookup"><span data-stu-id="9c29c-149">Suspicious</span></span>    | <span data-ttu-id="9c29c-150">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="9c29c-150">Devices or email content</span></span> | <span data-ttu-id="9c29c-151">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="9c29c-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="9c29c-152">找不到威脅</span><span class="sxs-lookup"><span data-stu-id="9c29c-152">No threats found</span></span>    | <span data-ttu-id="9c29c-153">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="9c29c-153">Devices or email content</span></span>    | <span data-ttu-id="9c29c-154">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="9c29c-155">手動採取的修正動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="9c29c-156">除了遵循自動調查的修復動作之外，您的安全性作業小組也可以手動採取某些修正動作。</span><span class="sxs-lookup"><span data-stu-id="9c29c-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="9c29c-157">包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="9c29c-157">These include the following:</span></span>

- <span data-ttu-id="9c29c-158">手動裝置動作，例如裝置隔離或檔隔離</span><span class="sxs-lookup"><span data-stu-id="9c29c-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="9c29c-159">手動電子郵件動作，例如虛刪除的電子郵件</span><span class="sxs-lookup"><span data-stu-id="9c29c-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="9c29c-160">裝置或電子郵件上的[高級搜尋](../defender-endpoint/advanced-hunting-overview.md)動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="9c29c-161">[Explorer](../office-365-security/threat-explorer.md) 對電子郵件內容的動作，例如將電子郵件移至垃圾郵件、虛刪除的電子郵件或實刪除的電子郵件</span><span class="sxs-lookup"><span data-stu-id="9c29c-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="9c29c-162">手動 [即時回應](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 動作，例如刪除檔案、停止程式及移除計畫任務</span><span class="sxs-lookup"><span data-stu-id="9c29c-162">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="9c29c-163">[Microsoft Defender For Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)的即時回應動作，例如隔離裝置、執行防病毒掃描，以及取得檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="9c29c-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="9c29c-164">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9c29c-164">Next steps</span></span>

- [<span data-ttu-id="9c29c-165">造訪重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="9c29c-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="9c29c-166">查看和管理修正動作</span><span class="sxs-lookup"><span data-stu-id="9c29c-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="9c29c-167">位址誤報或漏報</span><span class="sxs-lookup"><span data-stu-id="9c29c-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
