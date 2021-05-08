---
title: 服務方案的例外狀況
description: 如何要求標準服務方案的例外狀況
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 59a2b8227eb7e410ecf8506ce288978213537edc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245513"
---
# <a name="exceptions-to-the-service-plan"></a><span data-ttu-id="fa8d1-104">服務方案的例外狀況</span><span class="sxs-lookup"><span data-stu-id="fa8d1-104">Exceptions to the service plan</span></span>

<span data-ttu-id="fa8d1-105">Microsoft 受管理的電腦提供策劃裝置清單、[標準裝置設定](device-policies.md)、應用程式需求，以及特定的[可設定設定](../working-with-managed-desktop/config-setting-overview.md)，其設計目的都是為使用者提供安全、生產力和愉快的體驗。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-105">Microsoft Managed Desktop provides a curated device list, [standard device settings](device-policies.md), applications requirements, and certain [configurable settings](../working-with-managed-desktop/config-setting-overview.md), all designed to provide a secure, productive, and pleasant experience for users.</span></span> <span data-ttu-id="fa8d1-106">最好永遠保持服務的附帶。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-106">It’s best to always stay with the service as provided.</span></span> <span data-ttu-id="fa8d1-107">不過，我們認為服務的某些詳細資料可能無法完全符合您組織的需求。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-107">However, we recognize that some details of the service might not fit exactly with your organization’s needs.</span></span> <span data-ttu-id="fa8d1-108">如果您認為需要以某種方式變更服務，請務必遵循下列程式要求這些變更。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-108">If you feel you need to alter the service in some way, it’s important that you follow the following processes to request those changes.</span></span>
 
## <a name="types-of-exceptions"></a><span data-ttu-id="fa8d1-109">例外類型</span><span class="sxs-lookup"><span data-stu-id="fa8d1-109">Types of exceptions</span></span>

<span data-ttu-id="fa8d1-110">例外情況是任何新增或變更 Microsoft 受管理的電腦基本設定;範例範圍從 USB 埠設定到部署新的裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-110">An exception is any addition or change to the Microsoft Managed Desktop base configuration; examples range from USB ports configuration to deploying a new device driver.</span></span> <span data-ttu-id="fa8d1-111">我們會將各種例外狀況分組，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fa8d1-111">We group various exceptions as follows:</span></span>

|<span data-ttu-id="fa8d1-112">類型</span><span class="sxs-lookup"><span data-stu-id="fa8d1-112">Type</span></span>  |<span data-ttu-id="fa8d1-113">描述</span><span class="sxs-lookup"><span data-stu-id="fa8d1-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fa8d1-114">生產力軟體</span><span class="sxs-lookup"><span data-stu-id="fa8d1-114">Productivity software</span></span>     |  <span data-ttu-id="fa8d1-115">使用者需要的前景軟體，受限於 [應用程式需求](mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="fa8d1-115">Foreground software needed by users, restricted by the [application requirements](mmd-app-requirements.md)</span></span>       |
|<span data-ttu-id="fa8d1-116">& Vpn 的安全性代理程式</span><span class="sxs-lookup"><span data-stu-id="fa8d1-116">Security agents & VPNs</span></span>     |  <span data-ttu-id="fa8d1-117">用來保護、監視或變更裝置或網路行為的軟體</span><span class="sxs-lookup"><span data-stu-id="fa8d1-117">Software used to secure, monitor, or change the behavior of the device or network</span></span>       |
|<span data-ttu-id="fa8d1-118">數位經驗監控</span><span class="sxs-lookup"><span data-stu-id="fa8d1-118">Digital experience monitoring</span></span>     |  <span data-ttu-id="fa8d1-119">用來追蹤使用者設備上的資料以向其申報的軟體</span><span class="sxs-lookup"><span data-stu-id="fa8d1-119">Software used to track data on a user’s device to report to IT</span></span>       |
|<span data-ttu-id="fa8d1-120">硬體或軟體驅動程式</span><span class="sxs-lookup"><span data-stu-id="fa8d1-120">Hardware or software drivers</span></span>     |   <span data-ttu-id="fa8d1-121">裝置磁碟機，受限於 [應用程式需求](mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="fa8d1-121">Device drivers, restricted by the [application requirements](mmd-app-requirements.md)</span></span>      |
|<span data-ttu-id="fa8d1-122">原則</span><span class="sxs-lookup"><span data-stu-id="fa8d1-122">Policies</span></span>     | <span data-ttu-id="fa8d1-123">受管理裝置上的 Windows 10 或 Microsoft 365 Apps 企業版設定</span><span class="sxs-lookup"><span data-stu-id="fa8d1-123">Windows 10 or Microsoft 365 Apps for enterprise settings on a managed device</span></span>        |
|<span data-ttu-id="fa8d1-124">裝置</span><span class="sxs-lookup"><span data-stu-id="fa8d1-124">Devices</span></span>     | <span data-ttu-id="fa8d1-125">不在 Microsoft 受管理的電腦[裝置清單](device-list.md)上的裝置</span><span class="sxs-lookup"><span data-stu-id="fa8d1-125">Devices that are not on the Microsoft Managed Desktop [device list](device-list.md)</span></span>        |
|<span data-ttu-id="fa8d1-126">其他</span><span class="sxs-lookup"><span data-stu-id="fa8d1-126">Other</span></span>     |  <span data-ttu-id="fa8d1-127">其他地區未涵蓋的任何專案</span><span class="sxs-lookup"><span data-stu-id="fa8d1-127">Anything not covered by the other areas</span></span>       |
 
## <a name="request-an-exception"></a><span data-ttu-id="fa8d1-128">要求例外狀況</span><span class="sxs-lookup"><span data-stu-id="fa8d1-128">Request an exception</span></span>

<span data-ttu-id="fa8d1-129">建立變更要求，透過 Microsoft 受管理的電腦的管理入口網站提交要求。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-129">Submit requests through the Microsoft Managed Desktop Admin portal by creating a change request.</span></span> <span data-ttu-id="fa8d1-130">請務必包含下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="fa8d1-130">Be sure to include these details:</span></span>

- <span data-ttu-id="fa8d1-131">免除類型：是哪種例外狀況類別？</span><span class="sxs-lookup"><span data-stu-id="fa8d1-131">Exemption type: Which category of exception is it?</span></span> <span data-ttu-id="fa8d1-132"> (請參閱上一個表格) </span><span class="sxs-lookup"><span data-stu-id="fa8d1-132">(see the previous table)</span></span>
- <span data-ttu-id="fa8d1-133">需求：例外狀況的特定業務需求為何？</span><span class="sxs-lookup"><span data-stu-id="fa8d1-133">Requirement: What is the specific business requirement for the exception?</span></span>
- <span data-ttu-id="fa8d1-134">提案：您的業務要求是哪一個解決方案？</span><span class="sxs-lookup"><span data-stu-id="fa8d1-134">Proposal: Which solution is your business requesting?</span></span>
- <span data-ttu-id="fa8d1-135">時程表：您想要此例外狀況持續多久？</span><span class="sxs-lookup"><span data-stu-id="fa8d1-135">Timeline: How long do you want this exception to last?</span></span> 

## <a name="how-we-assess-an-exception-request"></a><span data-ttu-id="fa8d1-136">如何評估例外狀況要求</span><span class="sxs-lookup"><span data-stu-id="fa8d1-136">How we assess an exception request</span></span>

<span data-ttu-id="fa8d1-137">當我們查看例外要求時，我們會依下列順序評估這些因素：</span><span class="sxs-lookup"><span data-stu-id="fa8d1-137">When we review exception requests, we assess these factors in this order:</span></span>
 
1. <span data-ttu-id="fa8d1-138">Microsoft 受管理的電腦部署至所有裝置的某些應用程式和原則不可轉讓，所以您的要求不會影響這些裝置和原則。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-138">Some applications and policies which Microsoft Managed Desktop deploys to all devices aren't negotiable, so your request must not affect those.</span></span> <span data-ttu-id="fa8d1-139">如需詳細資訊，請參閱 [Device configuration](device-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-139">See [Device configuration](device-policies.md) for more information.</span></span>
2. <span data-ttu-id="fa8d1-140">使用者在執行工作時所需的受限制的生產力軟體，可能會受到核准。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-140">Restricted productivity software required by a user to do their job will likely be approved.</span></span> 
3. <span data-ttu-id="fa8d1-141">如果您使用 Microsoft 技術來滿足您的需求，我們可能會將您要求的例外遷移週期核准為3到12個月 (，視 project) 的範圍而定。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-141">If we can meet your requirement by using Microsoft technology, we’ll likely approve your request for an exception migration period of three to 12 months (depending on the scope of the project).</span></span>
4. <span data-ttu-id="fa8d1-142">如果您使用 Microsoft 技術無法滿足您的需求，我們可能會核准您的要求，除非違反下列其中一個條件。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-142">If we can’t meet your requirement by using Microsoft technology, we’ll likely approve your request unless it violates one of the conditions below.</span></span>  

<span data-ttu-id="fa8d1-143">這些原則可確保 Microsoft 受管理的電腦在追蹤標準範本的偏離時一定會符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-143">These principles ensure that Microsoft Managed Desktop can always meet your needs while tracking deviations from our standard template.</span></span> 

## <a name="key-conditions"></a><span data-ttu-id="fa8d1-144">主要條件</span><span class="sxs-lookup"><span data-stu-id="fa8d1-144">Key conditions</span></span>

<span data-ttu-id="fa8d1-145">我們會檢查例外狀況，以確保它們不會違反任何下列條件：</span><span class="sxs-lookup"><span data-stu-id="fa8d1-145">We review exceptions to ensure they don't violate any of these conditions:</span></span>

- <span data-ttu-id="fa8d1-146">例外狀況不一定會對系統安全性造成不良影響。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-146">An exception must not adversely impact system security.</span></span> 
- <span data-ttu-id="fa8d1-147">維護例外狀況不一定會對 Microsoft 受管理的電腦作業或支援產生大量的成本。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-147">Maintaining the exception must not incur a significant cost for either Microsoft Managed Desktop operations or support.</span></span>
- <span data-ttu-id="fa8d1-148">例外狀況不一定會影響系統穩定性，例如，由於導致核心模式損毀或懸掛。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-148">An exception must not affect system stability, for example, by causing kernel mode crashes or hangs.</span></span>
- <span data-ttu-id="fa8d1-149">變更不得限制我們運作服務或與核心 Microsoft 受管理的電腦技術產生衝突。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-149">The change must not restrict us from operating the service or conflict with core Microsoft Managed Desktop technology.</span></span>

<span data-ttu-id="fa8d1-150">這些情況以後可能會變更。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-150">These conditions could change in the future.</span></span> <span data-ttu-id="fa8d1-151">如果我們進行這類變更，我們會在這些條件生效之前提供30天的通知。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-151">If we do make such changes, we’ll provide 30 days notice prior to those conditions coming into effect.</span></span>  <span data-ttu-id="fa8d1-152">如果 Microsoft 受管理的電腦提供另一種方式來符合核准的例外狀況，Microsoft 受管理的電腦會通知客戶應 Microsoft 受管理的電腦變更支援例外狀況的方式。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-152">If Microsoft Managed Desktop delivers an alternative way to meet an approved exception, Microsoft Managed Desktop will notify the customer should Microsoft Managed Desktop alter the way in supporting the exception.</span></span> 

## <a name="revoking-approval-for-an-exception"></a><span data-ttu-id="fa8d1-153">撤銷例外狀況的核准</span><span class="sxs-lookup"><span data-stu-id="fa8d1-153">Revoking approval for an exception</span></span>

<span data-ttu-id="fa8d1-154">在核准和部署要求的例外狀況之後，我們可能會發現問題，即可能會發現，當我們在第一個位置核准變更時，可能會違反一些重要條件。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-154">After a requested exception is approved and deployed, it’s possible that we might discover problems that violate the key conditions that weren’t evident when we approved the change in the first place.</span></span> <span data-ttu-id="fa8d1-155">在此情況下，我們可能必須撤銷例外狀況的核准。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-155">In this situation, we might have to revoke approval for the exception.</span></span>
 
<span data-ttu-id="fa8d1-156">如果發生這種情況，我們會使用 Microsoft 受管理的電腦管理入口網站來通知您。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-156">If this happens, we’ll notify you by using the Microsoft Managed Desktop admin portal.</span></span> <span data-ttu-id="fa8d1-157">當我們第一次通知您時，您有90天可以移除例外狀況，直到出現例外狀況的裝置不再受到 Microsoft 受管理的電腦服務等級協定的限制。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-157">From the first time we notify you, you have 90 days to remove the exception before the devices with the exception are no longer bound by Microsoft Managed Desktop service level agreements.</span></span> <span data-ttu-id="fa8d1-158">根據嚴格的時程表，我們會傳送您多個通知，但嚴重的事件或威脅可能需要我們變更時程表或我們有關例外的決策。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-158">We'll send you several notifications according to a strict timeline--however, a severe incident or threat might require us to change the timeline or our decisions about an exception.</span></span> <span data-ttu-id="fa8d1-159">在未征征的情況下，我們不會 *移除* 例外狀況，但已撤銷例外狀況的任何裝置將不再受我們的服務等級協定的系結。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-159">We won't *remove* an exception without your consent, but any device with a revoked exception will no longer be bound by our service level agreement.</span></span> <span data-ttu-id="fa8d1-160">以下是即將傳送您的通知時程表：</span><span class="sxs-lookup"><span data-stu-id="fa8d1-160">Here is the timeline of notifications we will send you:</span></span>

- <span data-ttu-id="fa8d1-161">**第一個注意事項：** 我們會提供我們取消核准之決定的第一份通知，其中包括如何吊銷核准的相關資訊、建議採取的動作、這些動作的截止期限，以及如果您想要的決定，請採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-161">**First notice:** We provide the first notice of our decision to revoke approval, including information about why we’re revoking it, the actions we advise you to take, the deadline for those actions, and steps to follow if you want to appeal the decision.</span></span> <span data-ttu-id="fa8d1-162">在例外需要從所有裝置中移除之前，會提前90天。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-162">This notice occurs 90 days in advance before the exception needs to be removed from all devices.</span></span> 
- <span data-ttu-id="fa8d1-163">**第二個注意事項 (30 天之後) ：** 我們會提供第二個通知，包括第一個通知中所提供的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-163">**Second notice (30 days later):** We provide a second notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="fa8d1-164">第 **三個注意事項會在第一個通知) 之後 (60 天：** 我們提供第三個通知，包括第一個通知中所提供的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-164">**Third notice (60 days after the first notice):** We provide a third notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="fa8d1-165">**最後一個注意事項 (于90天的期限) ：** 我們提供第四個通知，包括第一個通知中所提供的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-165">**Final notice (one week before the 90-day deadline):** We provide a fourth notice, including the same information provided in the first notice.</span></span>
- <span data-ttu-id="fa8d1-166">**在第一次通知之後的90天：** Microsoft 受管理的電腦服務等級協定不再套用至具有已撤銷例外狀況的任何裝置。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-166">**90 days after first notice:** Microsoft Managed Desktop service level agreements no longer apply to any devices that have the revoked exception.</span></span> <span data-ttu-id="fa8d1-167">任何時候，您都可以挑戰決策，並提供其他資訊供您考慮，包括升級、設定變更或軟體變更。</span><span class="sxs-lookup"><span data-stu-id="fa8d1-167">At any time, you can challenge the decision and provide additional information for consideration, including upgrade, configuration changes, or change of software.</span></span> 


