---
title: 服務方案的例外狀況
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 826710bf59acd88494adf1f154e5657d1e039af7
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529932"
---
# <a name="exceptions-to-the-service-plan"></a><span data-ttu-id="db0af-103">服務方案的例外狀況</span><span class="sxs-lookup"><span data-stu-id="db0af-103">Exceptions to the service plan</span></span>

<span data-ttu-id="db0af-104">Microsoft 受管理的桌面提供策劃裝置清單、[標準裝置設定](device-policies.md)、應用程式需求，以及特定的[可設定設定](../working-with-managed-desktop/config-setting-overview.md)，其設計目的都是為使用者提供安全、生產力和愉快的體驗。</span><span class="sxs-lookup"><span data-stu-id="db0af-104">Microsoft Managed Desktop provides a curated device list, [standard device settings](device-policies.md), applications requirements, and certain [configurable settings](../working-with-managed-desktop/config-setting-overview.md), all designed to provide a secure, productive, and pleasant experience for end users.</span></span> <span data-ttu-id="db0af-105">最好永遠保持服務的附帶。</span><span class="sxs-lookup"><span data-stu-id="db0af-105">It’s best to always stay with the service as provided.</span></span> <span data-ttu-id="db0af-106">不過，我們認為服務的某些詳細資料可能無法完全符合您組織的需求。</span><span class="sxs-lookup"><span data-stu-id="db0af-106">However, we recognize that some details of the service might not fit exactly with your organization’s needs.</span></span> <span data-ttu-id="db0af-107">如果您認為需要以某種方式變更服務，請務必遵循下列程式要求這些變更。</span><span class="sxs-lookup"><span data-stu-id="db0af-107">If you feel you need to alter the service in some way, it’s important that you follow the following processes to request those changes.</span></span>
 
## <a name="types-of-exceptions"></a><span data-ttu-id="db0af-108">例外類型</span><span class="sxs-lookup"><span data-stu-id="db0af-108">Types of exceptions</span></span>

<span data-ttu-id="db0af-109">例外情況是任何新增或變更 Microsoft 受管理的桌面基本設定;範例範圍從 USB 埠設定到部署新的裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="db0af-109">An exception is any addition or change to the Microsoft Managed Desktop base configuration; examples range from USB ports configuration to deploying a new device driver.</span></span> <span data-ttu-id="db0af-110">我們會將各種例外狀況分組，如下所示：</span><span class="sxs-lookup"><span data-stu-id="db0af-110">We group various exceptions as follows:</span></span>

|<span data-ttu-id="db0af-111">類型</span><span class="sxs-lookup"><span data-stu-id="db0af-111">Type</span></span>  |<span data-ttu-id="db0af-112">描述</span><span class="sxs-lookup"><span data-stu-id="db0af-112">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="db0af-113">生產力軟體</span><span class="sxs-lookup"><span data-stu-id="db0af-113">Productivity software</span></span>     |  <span data-ttu-id="db0af-114">使用者需要的前臺軟體，受限於[應用程式需求](mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="db0af-114">Foreground software needed by end users, restricted by the [application requirements](mmd-app-requirements.md)</span></span>       |
|<span data-ttu-id="db0af-115">& Vpn 的安全性代理程式</span><span class="sxs-lookup"><span data-stu-id="db0af-115">Security agents & VPNs</span></span>     |  <span data-ttu-id="db0af-116">用來保護、監視或變更裝置或網路行為的軟體</span><span class="sxs-lookup"><span data-stu-id="db0af-116">Software used to secure, monitor, or change the behavior of the device or network</span></span>       |
|<span data-ttu-id="db0af-117">數位經驗監控</span><span class="sxs-lookup"><span data-stu-id="db0af-117">Digital experience monitoring</span></span>     |  <span data-ttu-id="db0af-118">用來追蹤使用者設備上的資料以向其申報的軟體</span><span class="sxs-lookup"><span data-stu-id="db0af-118">Software used to track data on a user’s device to report to IT</span></span>       |
|<span data-ttu-id="db0af-119">硬體或軟體驅動程式</span><span class="sxs-lookup"><span data-stu-id="db0af-119">Hardware or software drivers</span></span>     |   <span data-ttu-id="db0af-120">裝置磁碟機，受限於[應用程式需求](mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="db0af-120">Device drivers, restricted by the [application requirements](mmd-app-requirements.md)</span></span>      |
|<span data-ttu-id="db0af-121">原則</span><span class="sxs-lookup"><span data-stu-id="db0af-121">Policies</span></span>     | <span data-ttu-id="db0af-122">受管理裝置上的 Windows 10 或 Microsoft 365 應用程式的企業版設定</span><span class="sxs-lookup"><span data-stu-id="db0af-122">Windows 10 or Microsoft 365 Apps for enterprise settings on a managed device</span></span>        |
|<span data-ttu-id="db0af-123">裝置</span><span class="sxs-lookup"><span data-stu-id="db0af-123">Devices</span></span>     | <span data-ttu-id="db0af-124">不在 Microsoft 受管理的桌面[裝置清單](device-list.md)上的裝置</span><span class="sxs-lookup"><span data-stu-id="db0af-124">Devices which are not on the Microsoft Managed Desktop [device list](device-list.md)</span></span>        |
|<span data-ttu-id="db0af-125">其他</span><span class="sxs-lookup"><span data-stu-id="db0af-125">Other</span></span>     |  <span data-ttu-id="db0af-126">其他地區未涵蓋的任何專案</span><span class="sxs-lookup"><span data-stu-id="db0af-126">Anything not covered by the other areas</span></span>       |
 
## <a name="request-an-exception"></a><span data-ttu-id="db0af-127">要求例外狀況</span><span class="sxs-lookup"><span data-stu-id="db0af-127">Request an exception</span></span>

<span data-ttu-id="db0af-128">建立變更要求，透過 Microsoft Managed Desktop Admin 入口網站提交要求。</span><span class="sxs-lookup"><span data-stu-id="db0af-128">Submit requests through the Microsoft Managed Desktop Admin portal by creating a change request.</span></span> <span data-ttu-id="db0af-129">請務必包含下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="db0af-129">Be sure to include these details:</span></span>

-   <span data-ttu-id="db0af-130">免除類型：是哪種例外狀況類別？</span><span class="sxs-lookup"><span data-stu-id="db0af-130">Exemption type: Which category of exception is it?</span></span> <span data-ttu-id="db0af-131">（請參閱上一個表格）</span><span class="sxs-lookup"><span data-stu-id="db0af-131">(see the previous table)</span></span>
-   <span data-ttu-id="db0af-132">需求：例外狀況的特定業務需求為何？</span><span class="sxs-lookup"><span data-stu-id="db0af-132">Requirement: What is the specific business requirement for the exception?</span></span>
-   <span data-ttu-id="db0af-133">提案：您的業務要求是哪一個解決方案？</span><span class="sxs-lookup"><span data-stu-id="db0af-133">Proposal: Which solution is your business requesting?</span></span>
-   <span data-ttu-id="db0af-134">時程表：您想要此例外狀況持續多久？</span><span class="sxs-lookup"><span data-stu-id="db0af-134">Timeline: How long do you want this exception to last?</span></span> 

## <a name="how-we-assess-an-exception-request"></a><span data-ttu-id="db0af-135">如何評估例外狀況要求</span><span class="sxs-lookup"><span data-stu-id="db0af-135">How we assess an exception request</span></span>

<span data-ttu-id="db0af-136">當我們查看例外要求時，我們會依下列順序評估這些因素：</span><span class="sxs-lookup"><span data-stu-id="db0af-136">When we review exception requests, we assess these factors in this order:</span></span>
 
1.  <span data-ttu-id="db0af-137">Microsoft 受管理的桌面部署至所有裝置的某些應用程式和原則不可轉讓，因此您的要求不一定會影響這些應用程式和原則。</span><span class="sxs-lookup"><span data-stu-id="db0af-137">Some applications and policies which Microsoft Managed Desktop deploys to all devices aren't negotiable, so your request must not affect those.</span></span> <span data-ttu-id="db0af-138">如需詳細資訊，請參閱[Device configuration](device-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="db0af-138">See [Device configuration](device-policies.md) for more information.</span></span>
2.  <span data-ttu-id="db0af-139">使用者在執行工作時所需的受限制生產力軟體，可能會受到核准。</span><span class="sxs-lookup"><span data-stu-id="db0af-139">Restricted productivity software required by an end user to do their job will likely be approved.</span></span> 
3.  <span data-ttu-id="db0af-140">如果您使用 Microsoft 技術來符合您的需求，我們可能會將您的要求核准為三至十二個月的例外遷移週期（視專案範圍而定）。</span><span class="sxs-lookup"><span data-stu-id="db0af-140">If we can meet your requirement by using Microsoft technology, we’ll likely approve your request for an exception migration period of three to twelve months (depending on the scope of the project).</span></span>
4.  <span data-ttu-id="db0af-141">如果您使用 Microsoft 技術無法滿足您的需求，我們可能會核准您的要求，除非違反下列其中一個條件。</span><span class="sxs-lookup"><span data-stu-id="db0af-141">If we can’t meet your requirement by using Microsoft technology, we’ll likely approve your request unless it violates one of the conditions below.</span></span>  

<span data-ttu-id="db0af-142">這些原則確定 Microsoft 受管理的桌面可以在追蹤標準範本的偏差時，永遠符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="db0af-142">These principles ensure that Microsoft Managed Desktop can always meet your needs while tracking deviations from our standard template.</span></span> 

## <a name="key-conditions"></a><span data-ttu-id="db0af-143">主要條件</span><span class="sxs-lookup"><span data-stu-id="db0af-143">Key conditions</span></span>

<span data-ttu-id="db0af-144">我們會檢查例外狀況，以確保它們不會違反任何下列條件：</span><span class="sxs-lookup"><span data-stu-id="db0af-144">We review exceptions to ensure they don't violate any of these conditions:</span></span>

-   <span data-ttu-id="db0af-145">例外狀況不一定會對系統安全性造成不良影響。</span><span class="sxs-lookup"><span data-stu-id="db0af-145">An exception must not adversely impact system security.</span></span> 
-   <span data-ttu-id="db0af-146">維護例外狀況不一定會對 Microsoft 受管理的桌面作業或支援產生大量的成本。</span><span class="sxs-lookup"><span data-stu-id="db0af-146">Maintaining the exception must not incur a significant cost for either Microsoft Managed Desktop operations or support.</span></span>
-   <span data-ttu-id="db0af-147">例外狀況不一定會影響系統穩定性，例如，由於導致核心模式損毀或懸掛。</span><span class="sxs-lookup"><span data-stu-id="db0af-147">An exception must not affect system stability, for example, by causing kernel mode crashes or hangs.</span></span>
-   <span data-ttu-id="db0af-148">變更不得限制我們運作服務或與核心 Microsoft 受管理的桌面技術產生衝突。</span><span class="sxs-lookup"><span data-stu-id="db0af-148">The change must not restrict us from operating the service or conflict with core Microsoft Managed Desktop technology.</span></span>

<span data-ttu-id="db0af-149">這些情況以後可能會變更。</span><span class="sxs-lookup"><span data-stu-id="db0af-149">These conditions could change in the future.</span></span> <span data-ttu-id="db0af-150">如果我們進行這類變更，我們會在這些條件生效之前提供30天的通知。</span><span class="sxs-lookup"><span data-stu-id="db0af-150">If we do make such changes, we’ll provide 30 days notice prior to those conditions coming into effect.</span></span>  <span data-ttu-id="db0af-151">如果 Microsoft 受管理的桌面提供了另一種方式來符合核准的例外狀況，則 Microsoft 受管理的桌面會通知客戶 Microsoft 受管理的桌面會在支援例外狀況時，向客戶通知客戶。</span><span class="sxs-lookup"><span data-stu-id="db0af-151">If Microsoft Managed Desktop delivers an alternative way to meet an approved exception, Microsoft Managed Desktop will notify the customer should Microsoft Managed Desktop alter the way in supporting the exception.</span></span> 

## <a name="revoking-approval-for-an-exception"></a><span data-ttu-id="db0af-152">撤銷例外狀況的核准</span><span class="sxs-lookup"><span data-stu-id="db0af-152">Revoking approval for an exception</span></span>

<span data-ttu-id="db0af-153">在核准和部署要求的例外狀況之後，我們可能會發現問題，即可能會發現，當我們在第一個位置核准變更時，可能會違反一些重要條件。</span><span class="sxs-lookup"><span data-stu-id="db0af-153">After a requested exception is approved and deployed, it’s possible that we might discover problems that violate the key conditions that weren’t evident when we approved the change in the first place.</span></span> <span data-ttu-id="db0af-154">在此情況下，我們可能必須撤銷例外狀況的核准。</span><span class="sxs-lookup"><span data-stu-id="db0af-154">In this situation, we might have to revoke approval for the exception.</span></span>
 
<span data-ttu-id="db0af-155">如果發生這種情況，我們會使用 Microsoft Managed Desktop admin 入口網站通知您。</span><span class="sxs-lookup"><span data-stu-id="db0af-155">If this happens, we’ll notify you by using the Microsoft Managed Desktop admin portal.</span></span> <span data-ttu-id="db0af-156">當我們第一次通知您時，您有90天可以移除例外狀況，在具有例外狀況的裝置不再受到 Microsoft 受管理的桌面服務等級協定的限制之前。</span><span class="sxs-lookup"><span data-stu-id="db0af-156">From the first time we notify you, you have 90 days to remove the exception before the devices with the exception are no longer bound by Microsoft Managed Desktop service level agreements.</span></span> <span data-ttu-id="db0af-157">根據嚴格的時程表，我們會傳送您多個通知，但嚴重的事件或威脅可能需要我們變更時程表或我們有關例外的決策。</span><span class="sxs-lookup"><span data-stu-id="db0af-157">We'll send you several notifications according to a strict timeline--however, a severe incident or threat might require us to change the timeline or our decisions about an exception.</span></span> <span data-ttu-id="db0af-158">在未征征的情況下，我們不會*移除*例外狀況，但已撤銷例外狀況的任何裝置將不再受我們的服務等級協定的系結。</span><span class="sxs-lookup"><span data-stu-id="db0af-158">We won't *remove* an exception without your consent, but any device with a revoked exception will no longer be bound by our service level agreement.</span></span> <span data-ttu-id="db0af-159">以下是即將傳送您的通知時程表：</span><span class="sxs-lookup"><span data-stu-id="db0af-159">Here is the timeline of notifications we will send you:</span></span>

- <span data-ttu-id="db0af-160">**第一個注意事項：** 我們會提供我們取消核准之決定的第一份通知，其中包括如何吊銷核准的相關資訊、建議採取的動作、這些動作的截止期限，以及如果您想要的決定，請採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="db0af-160">**First notice:** We provide the first notice of our decision to revoke approval, including information about why we’re revoking it, the actions we advise you to take, the deadline for those actions, and steps to follow if you want to appeal the decision.</span></span> <span data-ttu-id="db0af-161">在例外需要從所有裝置中移除之前，這是一開始的90天。</span><span class="sxs-lookup"><span data-stu-id="db0af-161">This is 90 days in advance before the exception needs to be removed from all devices.</span></span> 
- <span data-ttu-id="db0af-162">**第二個通知（之後30天）：** 我們會提供第二個通知，包括第一個通知中所提供的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="db0af-162">**Second notice (30 days later):** We provide a second notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="db0af-163">**第三個通知（在第一個通知之後的60天）：** 我們提供第三個通知，包括第一個通知中所提供的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="db0af-163">**Third notice (60 days after the first notice):** We provide a third notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="db0af-164">**最後通知（90天截止日期前1周）：** 我們提供第四個通知，包括第一個通知中所提供的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="db0af-164">**Final notice (1 week before the 90-day deadline):** We provide a fourth notice, including the same information provided in the first notice.</span></span>
- <span data-ttu-id="db0af-165">**第一次通知之後的90天：** Microsoft 受管理的桌面服務層級協定不再適用于任何已撤銷例外狀況的裝置。</span><span class="sxs-lookup"><span data-stu-id="db0af-165">**90 days after first notice:** Microsoft Managed Desktop service level agreements no longer apply to any devices that have the revoked exception.</span></span> <span data-ttu-id="db0af-166">任何時候，您都可以挑戰決策，並提供其他資訊供您考慮，包括升級、設定變更或軟體變更。</span><span class="sxs-lookup"><span data-stu-id="db0af-166">At any time, you can challenge the decision and provide additional information for consideration, including upgrade, configuration changes, or change of software.</span></span> 


