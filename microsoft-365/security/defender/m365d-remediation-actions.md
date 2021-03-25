---
title: Microsoft 365 Defender 中的修正動作
description: 深入瞭解 Microsoft 365 Defender 中遵循自動調查的修復動作
keywords: automated, investigation, alert, trigger, action, remediation, 自動化, 調查, 警示, 觸發, 動作, 補救
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c81f824a0faaca1c228aa650c003576cce210a67
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199204"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="3920c-104">Microsoft 365 Defender 中的修正動作</span><span class="sxs-lookup"><span data-stu-id="3920c-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3920c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3920c-105">**Applies to:**</span></span>
- <span data-ttu-id="3920c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3920c-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="3920c-107">補救動作</span><span class="sxs-lookup"><span data-stu-id="3920c-107">Remediation actions</span></span>

<span data-ttu-id="3920c-108">在 Microsoft 365 Defender 中的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。</span><span class="sxs-lookup"><span data-stu-id="3920c-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="3920c-109">對裝置（也稱為端點）採取某些類型的修復動作。</span><span class="sxs-lookup"><span data-stu-id="3920c-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="3920c-110">對電子郵件內容採取其他修復動作。</span><span class="sxs-lookup"><span data-stu-id="3920c-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="3920c-111">在採取修正動作、核准或拒絕時，自動調查會完成。</span><span class="sxs-lookup"><span data-stu-id="3920c-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3920c-112">是否自動採取修復動作，也取決於特定設定，例如自動化程度。</span><span class="sxs-lookup"><span data-stu-id="3920c-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="3920c-113">若要深入瞭解，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="3920c-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="3920c-114">在 Microsoft 365 Defender 中設定您的自動化調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="3920c-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="3920c-115">如何在裝置上修正威脅</span><span class="sxs-lookup"><span data-stu-id="3920c-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="3920c-116">電子郵件 & 共同作業內容的威脅和修正動作</span><span class="sxs-lookup"><span data-stu-id="3920c-116">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="3920c-117">下表摘要說明 Microsoft 365 Defender 目前支援的修復動作：</span><span class="sxs-lookup"><span data-stu-id="3920c-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="3920c-118">裝置 (端點) 修正動作</span><span class="sxs-lookup"><span data-stu-id="3920c-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="3920c-119">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="3920c-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="3920c-120">-收集調查套件</span><span class="sxs-lookup"><span data-stu-id="3920c-120">- Collect investigation package</span></span> <br/><span data-ttu-id="3920c-121">-隔離裝置 (此動作可復原) </span><span class="sxs-lookup"><span data-stu-id="3920c-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="3920c-122">-下架電腦</span><span class="sxs-lookup"><span data-stu-id="3920c-122">- Offboard machine</span></span> <br/><span data-ttu-id="3920c-123">-發行程式碼執行</span><span class="sxs-lookup"><span data-stu-id="3920c-123">- Release code execution</span></span> <br/><span data-ttu-id="3920c-124">-從隔離區發行</span><span class="sxs-lookup"><span data-stu-id="3920c-124">- Release from quarantine</span></span> <br/><span data-ttu-id="3920c-125">-要求範例</span><span class="sxs-lookup"><span data-stu-id="3920c-125">- Request sample</span></span> <br/><span data-ttu-id="3920c-126">-限制執行程式碼執行 (此巨集指令可復原) </span><span class="sxs-lookup"><span data-stu-id="3920c-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="3920c-127">-執行防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="3920c-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="3920c-128">-停止和隔離</span><span class="sxs-lookup"><span data-stu-id="3920c-128">- Stop and quarantine</span></span>      |<span data-ttu-id="3920c-129">-)  (時，封鎖 URL</span><span class="sxs-lookup"><span data-stu-id="3920c-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="3920c-130">-虛刪除電子郵件訊息或聚簇</span><span class="sxs-lookup"><span data-stu-id="3920c-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="3920c-131">-隔離電子郵件</span><span class="sxs-lookup"><span data-stu-id="3920c-131">- Quarantine email</span></span><br/><span data-ttu-id="3920c-132">-隔離電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="3920c-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="3920c-133">-關閉外部郵件轉發</span><span class="sxs-lookup"><span data-stu-id="3920c-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="3920c-134">您可以在「 [行動中心](m365d-action-center.md)」查看修正動作（不論是待核准或已完成）。</span><span class="sxs-lookup"><span data-stu-id="3920c-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="3920c-135">遵循自動調查的修復動作</span><span class="sxs-lookup"><span data-stu-id="3920c-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="3920c-136">當自動調查完成時，所涉及的每一項證據都會達到序判定。</span><span class="sxs-lookup"><span data-stu-id="3920c-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="3920c-137">根據判定，修正動作的識別。</span><span class="sxs-lookup"><span data-stu-id="3920c-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="3920c-138">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="3920c-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="3920c-139">這完全取決於如何 [設定自動調查和回應](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="3920c-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="3920c-140">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="3920c-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="3920c-141">裁決</span><span class="sxs-lookup"><span data-stu-id="3920c-141">Verdict</span></span>    | <span data-ttu-id="3920c-142">範圍</span><span class="sxs-lookup"><span data-stu-id="3920c-142">Area</span></span>    | <span data-ttu-id="3920c-143">結果</span><span class="sxs-lookup"><span data-stu-id="3920c-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="3920c-144">惡意</span><span class="sxs-lookup"><span data-stu-id="3920c-144">Malicious</span></span>    | <span data-ttu-id="3920c-145">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="3920c-145">Devices (endpoints)</span></span>    | <span data-ttu-id="3920c-146">如果您組織的 [裝置群組](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) 會自動設定為 **完整修正威脅** ，便會自動採取修正動作 () </span><span class="sxs-lookup"><span data-stu-id="3920c-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="3920c-147">惡意</span><span class="sxs-lookup"><span data-stu-id="3920c-147">Malicious</span></span>    | <span data-ttu-id="3920c-148">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="3920c-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="3920c-149">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="3920c-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="3920c-150">可疑</span><span class="sxs-lookup"><span data-stu-id="3920c-150">Suspicious</span></span>    | <span data-ttu-id="3920c-151">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="3920c-151">Devices or email content</span></span> | <span data-ttu-id="3920c-152">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="3920c-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="3920c-153">找不到威脅</span><span class="sxs-lookup"><span data-stu-id="3920c-153">No threats found</span></span>    | <span data-ttu-id="3920c-154">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="3920c-154">Devices or email content</span></span>    | <span data-ttu-id="3920c-155">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="3920c-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="3920c-156">手動採取的修正動作</span><span class="sxs-lookup"><span data-stu-id="3920c-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="3920c-157">除了遵循自動調查的修復動作之外，您的安全性作業小組也可以手動採取某些修正動作。</span><span class="sxs-lookup"><span data-stu-id="3920c-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="3920c-158">包括下列動作：</span><span class="sxs-lookup"><span data-stu-id="3920c-158">These include the following actions:</span></span>

- <span data-ttu-id="3920c-159">手動裝置動作，例如裝置隔離或檔隔離。</span><span class="sxs-lookup"><span data-stu-id="3920c-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="3920c-160">手動電子郵件動作，例如虛刪除的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="3920c-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="3920c-161">裝置或電子郵件上的[高級搜尋](../defender-endpoint/advanced-hunting-overview.md)動作。</span><span class="sxs-lookup"><span data-stu-id="3920c-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="3920c-162">[Explorer](../office-365-security/threat-explorer.md) 對電子郵件內容的動作，例如將電子郵件移至垃圾郵件、虛刪除的電子郵件或實刪除的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3920c-162">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="3920c-163">手動 [即時回應](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 動作，例如刪除檔案、停止程式及移除排程的任務。</span><span class="sxs-lookup"><span data-stu-id="3920c-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="3920c-164">[Microsoft Defender For Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)的即時回應動作，例如隔離裝置、執行防病毒掃描，以及取得檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3920c-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="3920c-165">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3920c-165">Next steps</span></span>

- [<span data-ttu-id="3920c-166">造訪重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="3920c-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="3920c-167">查看和管理修正動作</span><span class="sxs-lookup"><span data-stu-id="3920c-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="3920c-168">在自動化調查和回應功能中處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="3920c-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
