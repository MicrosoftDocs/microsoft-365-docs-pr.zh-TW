---
title: Microsoft 365 Defender 中的補救動作
description: 取得 Microsoft 365 Defender 中遵循自動化調查的補救動作概觀
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
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932847"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="2f68c-104">Microsoft 365 Defender 中的補救動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2f68c-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="2f68c-105">**Applies to:**</span></span>
- <span data-ttu-id="2f68c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f68c-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="2f68c-107">補救動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-107">Remediation actions</span></span>

<span data-ttu-id="2f68c-108">在 Microsoft 365 Defender 的自動化調查期間和之後，會針對惡意或可疑專案識別補救動作。</span><span class="sxs-lookup"><span data-stu-id="2f68c-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="2f68c-109">某些類型的補救動作會針對裝置進行，也稱為端點。</span><span class="sxs-lookup"><span data-stu-id="2f68c-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="2f68c-110">對電子郵件內容採取其他補救動作。</span><span class="sxs-lookup"><span data-stu-id="2f68c-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="2f68c-111">在採取、核准或拒絕補救動作之後，自動化調查即完成。</span><span class="sxs-lookup"><span data-stu-id="2f68c-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f68c-112">要自動採取補救動作，或僅根據核准才進行修復動作，取決於某些設定，例如自動化層級的方式。</span><span class="sxs-lookup"><span data-stu-id="2f68c-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="2f68c-113">若要深入瞭解，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="2f68c-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="2f68c-114">在 Microsoft 365 Defender 中設定您的自動化調查及回應功能</span><span class="sxs-lookup"><span data-stu-id="2f68c-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="2f68c-115">如何在裝置上補救威脅</span><span class="sxs-lookup"><span data-stu-id="2f68c-115">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="2f68c-116">電子郵件和共同處理內容上的威脅&補救動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-116">Threats and remediation actions on email & collaboration content</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

<span data-ttu-id="2f68c-117">下表摘要列出 Microsoft 365 Defender 目前支援的補救動作：</span><span class="sxs-lookup"><span data-stu-id="2f68c-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="2f68c-118">裝置 (修復) 動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="2f68c-119">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-119">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="2f68c-120">- 收集調查套件</span><span class="sxs-lookup"><span data-stu-id="2f68c-120">- Collect investigation package</span></span> <br/><span data-ttu-id="2f68c-121">- 隔離裝置 (此動作可以復原) </span><span class="sxs-lookup"><span data-stu-id="2f68c-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="2f68c-122">- Offboard 電腦</span><span class="sxs-lookup"><span data-stu-id="2f68c-122">- Offboard machine</span></span> <br/><span data-ttu-id="2f68c-123">- 發行代碼執行</span><span class="sxs-lookup"><span data-stu-id="2f68c-123">- Release code execution</span></span> <br/><span data-ttu-id="2f68c-124">- 從隔離中釋出</span><span class="sxs-lookup"><span data-stu-id="2f68c-124">- Release from quarantine</span></span> <br/><span data-ttu-id="2f68c-125">- 要求範例</span><span class="sxs-lookup"><span data-stu-id="2f68c-125">- Request sample</span></span> <br/><span data-ttu-id="2f68c-126">- 限制程式碼 (此動作可以復原) </span><span class="sxs-lookup"><span data-stu-id="2f68c-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="2f68c-127">- 執行防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="2f68c-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="2f68c-128">- 停止和隔離</span><span class="sxs-lookup"><span data-stu-id="2f68c-128">- Stop and quarantine</span></span>      |<span data-ttu-id="2f68c-129">- 封鎖 (按一下滑鼠的網址) </span><span class="sxs-lookup"><span data-stu-id="2f68c-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="2f68c-130">- 柔式刪除電子郵件訊息或郵件組</span><span class="sxs-lookup"><span data-stu-id="2f68c-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="2f68c-131">- 隔離電子郵件</span><span class="sxs-lookup"><span data-stu-id="2f68c-131">- Quarantine email</span></span><br/><span data-ttu-id="2f68c-132">- 隔離電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="2f68c-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="2f68c-133">- 關閉外部郵件轉寄功能</span><span class="sxs-lookup"><span data-stu-id="2f68c-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="2f68c-134">您可以在控制中心中查看待核准或已完成的補救 [動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)。</span><span class="sxs-lookup"><span data-stu-id="2f68c-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="2f68c-135">追蹤自動化調查的補救動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="2f68c-136">完成自動化調查時，會針對每一個涉及的證明進行調查。</span><span class="sxs-lookup"><span data-stu-id="2f68c-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="2f68c-137">根據補救方式，識別補救動作。</span><span class="sxs-lookup"><span data-stu-id="2f68c-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="2f68c-138">在某些情況下，系統會自動進行修正動作；在其他情況下，修正動作需要核准。</span><span class="sxs-lookup"><span data-stu-id="2f68c-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="2f68c-139">這完全取決於您如何進行 [自動化調查與回應](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="2f68c-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="2f68c-140">下表列出可能的裁決和結果：</span><span class="sxs-lookup"><span data-stu-id="2f68c-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="2f68c-141">裁決</span><span class="sxs-lookup"><span data-stu-id="2f68c-141">Verdict</span></span>    | <span data-ttu-id="2f68c-142">範圍</span><span class="sxs-lookup"><span data-stu-id="2f68c-142">Area</span></span>    | <span data-ttu-id="2f68c-143">結果</span><span class="sxs-lookup"><span data-stu-id="2f68c-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="2f68c-144">惡意</span><span class="sxs-lookup"><span data-stu-id="2f68c-144">Malicious</span></span>    | <span data-ttu-id="2f68c-145">裝置 (端點)</span><span class="sxs-lookup"><span data-stu-id="2f68c-145">Devices (endpoints)</span></span>    | <span data-ttu-id="2f68c-146">假設貴組織的裝置 (設定為完整 **-** 自動修復威脅 [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)，就會自動採取補救) </span><span class="sxs-lookup"><span data-stu-id="2f68c-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="2f68c-147">惡意</span><span class="sxs-lookup"><span data-stu-id="2f68c-147">Malicious</span></span>    | <span data-ttu-id="2f68c-148">電子郵件內容 (URL 或附件)</span><span class="sxs-lookup"><span data-stu-id="2f68c-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="2f68c-149">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="2f68c-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="2f68c-150">可疑</span><span class="sxs-lookup"><span data-stu-id="2f68c-150">Suspicious</span></span>    | <span data-ttu-id="2f68c-151">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="2f68c-151">Devices or email content</span></span> | <span data-ttu-id="2f68c-152">建議的修正動作待核准</span><span class="sxs-lookup"><span data-stu-id="2f68c-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="2f68c-153">找不到任何威脅</span><span class="sxs-lookup"><span data-stu-id="2f68c-153">No threats found</span></span>    | <span data-ttu-id="2f68c-154">裝置或電子郵件內容</span><span class="sxs-lookup"><span data-stu-id="2f68c-154">Devices or email content</span></span>    | <span data-ttu-id="2f68c-155">不需要修正動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="2f68c-156">手動採取的補救動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="2f68c-157">除了遵循自動化調查的補救動作，您的安全性作業小組可以手動採取特定的補救動作。</span><span class="sxs-lookup"><span data-stu-id="2f68c-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="2f68c-158">這些動作包括下列動作：</span><span class="sxs-lookup"><span data-stu-id="2f68c-158">These include the following actions:</span></span>

- <span data-ttu-id="2f68c-159">手動裝置動作，例如裝置隔離或檔案隔離。</span><span class="sxs-lookup"><span data-stu-id="2f68c-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="2f68c-160">手動電子郵件動作，例如手動刪除電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="2f68c-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="2f68c-161">[裝置或](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) 電子郵件上的進一步搜尋動作。</span><span class="sxs-lookup"><span data-stu-id="2f68c-161">[Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="2f68c-162">[在](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 電子郵件內容上執行 Explorer 動作，例如將電子郵件移動至垃圾郵件、使用柔式刪除電子郵件，或硬式刪除電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2f68c-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="2f68c-163">手動 [即時回應](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 動作，例如刪除檔案、停止程式，以及移除已排程的工作。</span><span class="sxs-lookup"><span data-stu-id="2f68c-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="2f68c-164">使用 Microsoft [Defender 端點](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)API 執行即時回應動作，例如隔離裝置、執行防毒掃描，以及取得檔案相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2f68c-164">Live response action with [Microsoft Defender for Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="2f68c-165">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2f68c-165">Next steps</span></span>

- [<span data-ttu-id="2f68c-166">造訪重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="2f68c-166">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="2f68c-167">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="2f68c-167">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="2f68c-168">在自動化調查與回應功能中處理誤對/負數</span><span class="sxs-lookup"><span data-stu-id="2f68c-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
