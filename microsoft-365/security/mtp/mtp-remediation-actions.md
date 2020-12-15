---
title: Microsoft 365 Defender 中的修正動作
description: 深入瞭解 Microsoft 365 Defender 中遵循自動調查的修復動作
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9e489e3b0100aa138b11d4bfb4ccc8048a2113f4
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683292"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="35b14-104">Microsoft 365 Defender 中的修正動作</span><span class="sxs-lookup"><span data-stu-id="35b14-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="35b14-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="35b14-105">**Applies to:**</span></span>
- <span data-ttu-id="35b14-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35b14-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="35b14-107">補救動作</span><span class="sxs-lookup"><span data-stu-id="35b14-107">Remediation actions</span></span>

<span data-ttu-id="35b14-108">在 Microsoft 365 Defender 中的自動調查期間和之後，會針對惡意或可疑專案識別修正動作。</span><span class="sxs-lookup"><span data-stu-id="35b14-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="35b14-109">對裝置（也稱為端點）採取某些類型的修復動作。</span><span class="sxs-lookup"><span data-stu-id="35b14-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="35b14-110">對電子郵件內容採取其他修復動作。</span><span class="sxs-lookup"><span data-stu-id="35b14-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="35b14-111">在採取修正動作、核准或拒絕時，自動調查會完成。</span><span class="sxs-lookup"><span data-stu-id="35b14-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35b14-112">是否自動採取修復動作，也取決於特定設定，例如自動化程度。</span><span class="sxs-lookup"><span data-stu-id="35b14-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="35b14-113">若要深入瞭解，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="35b14-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="35b14-114">在 Microsoft 365 Defender 中設定您的自動化調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="35b14-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="35b14-115">如何在裝置上修正威脅</span><span class="sxs-lookup"><span data-stu-id="35b14-115">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="35b14-116">電子郵件 & 共同作業內容的威脅和修正動作</span><span class="sxs-lookup"><span data-stu-id="35b14-116">Threats and remediation actions on email & collaboration content</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

<span data-ttu-id="35b14-117">下表摘要說明 Microsoft 365 Defender 目前支援的修復動作：</span><span class="sxs-lookup"><span data-stu-id="35b14-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="35b14-118">裝置 (端點) 修正動作</span><span class="sxs-lookup"><span data-stu-id="35b14-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="35b14-119">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="35b14-119">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="35b14-120">-收集調查套件</span><span class="sxs-lookup"><span data-stu-id="35b14-120">- Collect investigation package</span></span> <br/><span data-ttu-id="35b14-121">-隔離裝置 (此動作可復原) </span><span class="sxs-lookup"><span data-stu-id="35b14-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="35b14-122">-下架電腦</span><span class="sxs-lookup"><span data-stu-id="35b14-122">- Offboard machine</span></span> <br/><span data-ttu-id="35b14-123">-發行程式碼執行</span><span class="sxs-lookup"><span data-stu-id="35b14-123">- Release code execution</span></span> <br/><span data-ttu-id="35b14-124">-從隔離區發行</span><span class="sxs-lookup"><span data-stu-id="35b14-124">- Release from quarantine</span></span> <br/><span data-ttu-id="35b14-125">-要求範例</span><span class="sxs-lookup"><span data-stu-id="35b14-125">- Request sample</span></span> <br/><span data-ttu-id="35b14-126">-限制執行程式碼執行 (此巨集指令可復原) </span><span class="sxs-lookup"><span data-stu-id="35b14-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="35b14-127">-執行防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="35b14-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="35b14-128">-停止和隔離</span><span class="sxs-lookup"><span data-stu-id="35b14-128">- Stop and quarantine</span></span>      |<span data-ttu-id="35b14-129">-)  (時，封鎖 URL</span><span class="sxs-lookup"><span data-stu-id="35b14-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="35b14-130">-虛刪除電子郵件訊息或聚簇</span><span class="sxs-lookup"><span data-stu-id="35b14-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="35b14-131">-隔離電子郵件</span><span class="sxs-lookup"><span data-stu-id="35b14-131">- Quarantine email</span></span><br/><span data-ttu-id="35b14-132">-隔離電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="35b14-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="35b14-133">-關閉外部郵件轉發</span><span class="sxs-lookup"><span data-stu-id="35b14-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="35b14-134">您可以在「 [行動中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)」查看修正動作（不論是待核准或已完成）。</span><span class="sxs-lookup"><span data-stu-id="35b14-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="35b14-135">遵循自動調查的修復動作</span><span class="sxs-lookup"><span data-stu-id="35b14-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="35b14-136">當自動調查完成時，所涉及的每一項證據都會達到序判定。</span><span class="sxs-lookup"><span data-stu-id="35b14-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="35b14-137">根據判定，修正動作的識別。</span><span class="sxs-lookup"><span data-stu-id="35b14-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="35b14-138">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="35b14-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="35b14-139">這完全取決於如何 [設定自動調查和回應](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="35b14-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="35b14-140">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="35b14-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="35b14-141">裁決</span><span class="sxs-lookup"><span data-stu-id="35b14-141">Verdict</span></span>    | <span data-ttu-id="35b14-142">範圍</span><span class="sxs-lookup"><span data-stu-id="35b14-142">Area</span></span>    | <span data-ttu-id="35b14-143">結果</span><span class="sxs-lookup"><span data-stu-id="35b14-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="35b14-144">惡意</span><span class="sxs-lookup"><span data-stu-id="35b14-144">Malicious</span></span>    | <span data-ttu-id="35b14-145">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="35b14-145">Devices (endpoints)</span></span>    | <span data-ttu-id="35b14-146">如果您組織的 [裝置群組](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) 會自動設定為 **完整修正威脅** ，便會自動採取修正動作 () </span><span class="sxs-lookup"><span data-stu-id="35b14-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="35b14-147">惡意</span><span class="sxs-lookup"><span data-stu-id="35b14-147">Malicious</span></span>    | <span data-ttu-id="35b14-148">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="35b14-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="35b14-149">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="35b14-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="35b14-150">可疑</span><span class="sxs-lookup"><span data-stu-id="35b14-150">Suspicious</span></span>    | <span data-ttu-id="35b14-151">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="35b14-151">Devices or email content</span></span> | <span data-ttu-id="35b14-152">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="35b14-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="35b14-153">找不到威脅</span><span class="sxs-lookup"><span data-stu-id="35b14-153">No threats found</span></span>    | <span data-ttu-id="35b14-154">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="35b14-154">Devices or email content</span></span>    | <span data-ttu-id="35b14-155">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="35b14-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="35b14-156">手動採取的修正動作</span><span class="sxs-lookup"><span data-stu-id="35b14-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="35b14-157">除了遵循自動調查的修復動作之外，您的安全性作業小組也可以手動採取某些修正動作。</span><span class="sxs-lookup"><span data-stu-id="35b14-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="35b14-158">包括下列動作：</span><span class="sxs-lookup"><span data-stu-id="35b14-158">These include the following actions:</span></span>

- <span data-ttu-id="35b14-159">手動裝置動作，例如裝置隔離或檔隔離。</span><span class="sxs-lookup"><span data-stu-id="35b14-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="35b14-160">手動電子郵件動作，例如虛刪除的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="35b14-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="35b14-161">裝置或電子郵件上的[高級搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)動作。</span><span class="sxs-lookup"><span data-stu-id="35b14-161">[Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="35b14-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 對電子郵件內容的動作，例如將電子郵件移至垃圾郵件、虛刪除的電子郵件或實刪除的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="35b14-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="35b14-163">手動 [即時回應](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 動作，例如刪除檔案、停止程式及移除排程的任務。</span><span class="sxs-lookup"><span data-stu-id="35b14-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="35b14-164">[Microsoft Defender For Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)的即時回應動作，例如隔離裝置、執行防病毒掃描，以及取得檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="35b14-164">Live response action with [Microsoft Defender for Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="35b14-165">後續步驟</span><span class="sxs-lookup"><span data-stu-id="35b14-165">Next steps</span></span>

- [<span data-ttu-id="35b14-166">造訪重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="35b14-166">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="35b14-167">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="35b14-167">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="35b14-168">在自動化調查和回應功能中處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="35b14-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
