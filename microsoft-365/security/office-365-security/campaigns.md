---
title: ATP 中的市場即時檢視
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解 Office 365 進階威脅防護中的行銷活動檢視。
ms.openlocfilehash: 5441c877dac70330bf1e5653983494be5b1b3293
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209592"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="b0660-103">ATP 中的即時檢視</span><span class="sxs-lookup"><span data-stu-id="b0660-103">Campaign Views in ATP</span></span>

<span data-ttu-id="b0660-104">[活動] 視圖是「安全性 & 規範中心」中的高級威脅防護（ATP）中的一項功能，可用於識別和分類服務中的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="b0660-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="b0660-105">行銷活動檢視可協助您：</span><span class="sxs-lookup"><span data-stu-id="b0660-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="b0660-106">更有效率地調查和回應網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="b0660-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="b0660-107">更進一步了解攻擊範圍。</span><span class="sxs-lookup"><span data-stu-id="b0660-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="b0660-108">向決策者展現價值。</span><span class="sxs-lookup"><span data-stu-id="b0660-108">Show value to decision makers.</span></span>

<span data-ttu-id="b0660-109">行銷活動檢視可讓您較任何人類所能夠，更快速且更完整地查看攻擊的全貌。</span><span class="sxs-lookup"><span data-stu-id="b0660-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="b0660-110">什麼是行銷活動？</span><span class="sxs-lookup"><span data-stu-id="b0660-110">What is a campaign?</span></span>

<span data-ttu-id="b0660-111">行銷活動是針對一或多個組織的協調式電子郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="b0660-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="b0660-112">竊取認證及公司資料的電子郵件攻擊是一種大型且 lucrative 的行業。</span><span class="sxs-lookup"><span data-stu-id="b0660-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="b0660-113">隨著技術不斷增加以停止攻擊的努力，攻擊者會修改其方法，以確保持續成功。</span><span class="sxs-lookup"><span data-stu-id="b0660-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="b0660-114">Microsoft 會利用整個服務中大量的反網路釣魚、反垃圾郵件和反惡意程式碼資料，協助識別市場活動。</span><span class="sxs-lookup"><span data-stu-id="b0660-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="b0660-115">我們會根據數個因素來分析和分類攻擊資訊。</span><span class="sxs-lookup"><span data-stu-id="b0660-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="b0660-116">例如：</span><span class="sxs-lookup"><span data-stu-id="b0660-116">For example:</span></span>

- <span data-ttu-id="b0660-117">**攻擊來源**：來源 IP 位址和寄件者電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="b0660-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="b0660-118">**攻擊訊息屬性**：攻擊訊息的內容、樣式和調性。</span><span class="sxs-lookup"><span data-stu-id="b0660-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="b0660-119">**攻擊收件者**：收件者網域、收件者工作職掌 (系統管理員、執行人員等)、公司類型 (大型、小型、公有、私人等等) 以及產業。</span><span class="sxs-lookup"><span data-stu-id="b0660-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="b0660-120">**攻擊負載**：攻擊郵件中的惡意連結、附件或其他負載。</span><span class="sxs-lookup"><span data-stu-id="b0660-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="b0660-121">市場活動可能會短期，或可能跨越數天、數周或數天，具有有效和非使用中的期間。</span><span class="sxs-lookup"><span data-stu-id="b0660-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="b0660-122">您的特定組織可能會發起一個市場活動，否則您的組織可能會是多個公司的較大活動的一部分。</span><span class="sxs-lookup"><span data-stu-id="b0660-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="b0660-123">即時檢視安全性 & 規範中心</span><span class="sxs-lookup"><span data-stu-id="b0660-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="b0660-124">在**威脅管理**活動中，[安全性 & 合規性中心](https://protection.office.com)提供即時檢視 \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="b0660-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![安全性與合規性中心的行銷活動概觀](../../media/campaigns-overview.png)

<span data-ttu-id="b0660-126">您也可以從下列來源取得市場即時檢視：</span><span class="sxs-lookup"><span data-stu-id="b0660-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="b0660-127">**威脅管理** \>**瀏覽器** \>**View** \>**活動**</span><span class="sxs-lookup"><span data-stu-id="b0660-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="b0660-128">**威脅管理** \>**瀏覽器** \>**View** \>**所有電子郵件** \>**活動**</span><span class="sxs-lookup"><span data-stu-id="b0660-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="b0660-129">如果您沒有看到任何行銷活動資料，請嘗試變更日期範圍。</span><span class="sxs-lookup"><span data-stu-id="b0660-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="b0660-130">概觀頁面會顯示有關行銷活動的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b0660-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="b0660-131">**名稱**</span><span class="sxs-lookup"><span data-stu-id="b0660-131">**Name**</span></span>

- <span data-ttu-id="b0660-132">**樣本主旨**：行銷活動中其中一個訊息的主旨列。</span><span class="sxs-lookup"><span data-stu-id="b0660-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="b0660-133">請注意，市場活動中的所有郵件不一定會有相同的主語。</span><span class="sxs-lookup"><span data-stu-id="b0660-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="b0660-134">**類型**：目前，此值永遠為**網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="b0660-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="b0660-135">**子類型**：本行銷活動要網路釣魚的品牌 (如適用)。</span><span class="sxs-lookup"><span data-stu-id="b0660-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="b0660-136">當以 ATP 技術為偵測時，會將前置詞**ATP**新增至子類型值。</span><span class="sxs-lookup"><span data-stu-id="b0660-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="b0660-137">**收件者**：此行銷活動鎖定的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="b0660-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="b0660-138">**Inboxed**：從其收件匣的此活動接收郵件的使用者人數（未傳遞至垃圾郵件）。</span><span class="sxs-lookup"><span data-stu-id="b0660-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="b0660-139">**按一下**：在網路釣魚郵件中按一下 URL 的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="b0660-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="b0660-140">**按一下 [速率**：由「已**按一下**Inboxed」所計算的百分比  /  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="b0660-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="b0660-141">此值是活動之效能的指示器，以及收件者是否可以將郵件識別為網路釣魚，並避免按一下 [負載 URL]。</span><span class="sxs-lookup"><span data-stu-id="b0660-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="b0660-142">已**訪問**：有多少使用者實際將其設為 [負載] 網站。</span><span class="sxs-lookup"><span data-stu-id="b0660-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="b0660-143">如果有**按一下**的值，但安全連結已封鎖網站的存取權，這個值將會是零。</span><span class="sxs-lookup"><span data-stu-id="b0660-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="b0660-144">當您按一下行銷活動的名稱時，行銷活動詳細資料會顯示在飛出視窗中。</span><span class="sxs-lookup"><span data-stu-id="b0660-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="b0660-145">行銷活動詳細資料</span><span class="sxs-lookup"><span data-stu-id="b0660-145">Campaign details</span></span>

<span data-ttu-id="b0660-146">在行銷活動詳細資料檢視中，提供有關行銷活動的許多資訊：</span><span class="sxs-lookup"><span data-stu-id="b0660-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="b0660-147">行銷活動資訊：</span><span class="sxs-lookup"><span data-stu-id="b0660-147">Campaign information:</span></span>

  - <span data-ttu-id="b0660-148">**識別碼**：唯一的活動識別碼。</span><span class="sxs-lookup"><span data-stu-id="b0660-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="b0660-149">**開始**和**結束**：您選取的日期範圍篩選。</span><span class="sxs-lookup"><span data-stu-id="b0660-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="b0660-150">**影響**：您選取的日期範圍篩選器的下列資料：</span><span class="sxs-lookup"><span data-stu-id="b0660-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="b0660-151">收件者總數。</span><span class="sxs-lookup"><span data-stu-id="b0660-151">The total number of recipients.</span></span>

    - <span data-ttu-id="b0660-152">「Inboxed」的郵件數目（也就是傳遞至收件匣，而非垃圾郵件）。</span><span class="sxs-lookup"><span data-stu-id="b0660-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="b0660-153">在網路釣魚郵件中按一下 URL 負載的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="b0660-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="b0660-154">Howe 許多使用者已訪問 URL。</span><span class="sxs-lookup"><span data-stu-id="b0660-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="b0660-155">行銷活動時間表：行銷活動的開始和結束時間，以及一段時間內的訊息量。</span><span class="sxs-lookup"><span data-stu-id="b0660-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="b0660-156">行銷活動流程</span><span class="sxs-lookup"><span data-stu-id="b0660-156">Campaign flow</span></span>

<span data-ttu-id="b0660-157">有關行銷活動的重要詳細資料，會在 [流程]\*\*\*\* 區段中的水平流程圖 (稱為 _Sankey_ 圖表) 中顯示。</span><span class="sxs-lookup"><span data-stu-id="b0660-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="b0660-158">這些詳細資料將協助您了解行銷活動的元素和在組織中的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="b0660-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![未包含使用者 URL 點選的行銷活動詳細資料](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="b0660-160">如果您將游標停留在圖表中的水平帶狀上，您會看到相關訊息的數量 (例如來自特定來源 IP 的訊息、來自使用特定寄件者網域來源 IP 的訊息等)。</span><span class="sxs-lookup"><span data-stu-id="b0660-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="b0660-161">圖表中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b0660-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="b0660-162">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="b0660-162">**Sender IPs**</span></span>

- <span data-ttu-id="b0660-163">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="b0660-163">**Sender domains**</span></span>

- <span data-ttu-id="b0660-164">**篩選 verdicts**：以下是與[反垃圾郵件訊息標頭](anti-spam-message-headers.md)中所述的可用網路釣魚和垃圾郵件篩選 verdicts 相關的值。</span><span class="sxs-lookup"><span data-stu-id="b0660-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="b0660-165">下表說明可用的值：</span><span class="sxs-lookup"><span data-stu-id="b0660-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="b0660-166">值</span><span class="sxs-lookup"><span data-stu-id="b0660-166">Value</span></span>|<span data-ttu-id="b0660-167">垃圾郵件篩選判定</span><span class="sxs-lookup"><span data-stu-id="b0660-167">Spam filter verdict</span></span>|<span data-ttu-id="b0660-168">描述</span><span class="sxs-lookup"><span data-stu-id="b0660-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="b0660-169">**允許**</span><span class="sxs-lookup"><span data-stu-id="b0660-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="b0660-170">垃圾郵件篩選功能（例如郵件流程規則，也稱為傳輸規則）進行評估之前，郵件會標示為非垃圾郵件和/或略過的篩選。</span><span class="sxs-lookup"><span data-stu-id="b0660-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="b0660-171">郵件因其他原因而略過垃圾郵件篩選（例如，寄件者和收件者似乎位於相同組織中）。</span><span class="sxs-lookup"><span data-stu-id="b0660-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="b0660-172">**已封鎖**</span><span class="sxs-lookup"><span data-stu-id="b0660-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="b0660-173">垃圾郵件篩選功能（例如，依郵件流程規則）進行評估之前，郵件已標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="b0660-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="b0660-174">**已偵測**</span><span class="sxs-lookup"><span data-stu-id="b0660-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="b0660-175">垃圾郵件篩選已將郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="b0660-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="b0660-176">**未偵測到**</span><span class="sxs-lookup"><span data-stu-id="b0660-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="b0660-177">郵件已由垃圾郵件篩選標示為非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="b0660-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="b0660-178">**釋放**</span><span class="sxs-lookup"><span data-stu-id="b0660-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="b0660-179">郵件因從隔離區發行而略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="b0660-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="b0660-180">**承租人允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b0660-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="b0660-181">由於反垃圾郵件原則設定，郵件會略過垃圾郵件篩選（例如，寄件者位於允許的寄件者清單或允許的網域清單中）。</span><span class="sxs-lookup"><span data-stu-id="b0660-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="b0660-182">**租使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b0660-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="b0660-183">由於反垃圾郵件原則設定（例如，寄件者位於允許的寄件者清單或允許的網域清單），垃圾郵件篩選會封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="b0660-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="b0660-184">**使用者允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b0660-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="b0660-185">郵件會略過垃圾郵件篩選，因為寄件者是在 Outlook 中的使用者的安全寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="b0660-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="b0660-186">**使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b0660-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="b0660-187">郵件被垃圾郵件篩選封鎖，因為寄件者位於 Outlook 中使用者的封鎖寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="b0660-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="b0660-188">**幹掉**</span><span class="sxs-lookup"><span data-stu-id="b0660-188">**ZAP**</span></span>|<span data-ttu-id="b0660-189">n/a</span><span class="sxs-lookup"><span data-stu-id="b0660-189">n/a</span></span>|<span data-ttu-id="b0660-190">[零小時自動清除（ZAP）](zero-hour-auto-purge.md)會根據您的反垃圾郵件原則設定（移至 [垃圾郵件] 資料夾或「隔離」），對傳送的郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="b0660-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="b0660-191"><sup>\*</sup>請複查您的反垃圾郵件原則，因為服務可能封鎖允許的郵件。</span><span class="sxs-lookup"><span data-stu-id="b0660-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="b0660-192"><sup>\*\*</sup>請複查您的反垃圾郵件原則，因為應該隔離這些郵件，而非傳遞。</span><span class="sxs-lookup"><span data-stu-id="b0660-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="b0660-193">**傳送位置**：您可能想要調查實際傳送給收件者的訊息 (無論是移至 [收件匣] 或 [垃圾郵件] 資料夾)，即使使用者未在訊息中點選承載 URL。</span><span class="sxs-lookup"><span data-stu-id="b0660-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="b0660-194">您也可以從隔離區中移除隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="b0660-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="b0660-195">如需詳細資訊，請參閱[在 EOP 中隔離的電子郵件訊息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b0660-195">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="b0660-196">**已刪除資料夾**</span><span class="sxs-lookup"><span data-stu-id="b0660-196">**Deleted folder**</span></span>

  - <span data-ttu-id="b0660-197">**下降**</span><span class="sxs-lookup"><span data-stu-id="b0660-197">**Dropped**</span></span>

  - <span data-ttu-id="b0660-198">**外部**：收件者位於您的內部部署電子郵件組織中。</span><span class="sxs-lookup"><span data-stu-id="b0660-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="b0660-199">**失敗**</span><span class="sxs-lookup"><span data-stu-id="b0660-199">**Failed**</span></span>

  - <span data-ttu-id="b0660-200">**轉發**</span><span class="sxs-lookup"><span data-stu-id="b0660-200">**Forwarded**</span></span>

  - <span data-ttu-id="b0660-201">**收件匣**</span><span class="sxs-lookup"><span data-stu-id="b0660-201">**Inbox**</span></span>

  - <span data-ttu-id="b0660-202">**垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="b0660-202">**Junk folder**</span></span>

  - <span data-ttu-id="b0660-203">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="b0660-203">**Quarantine**</span></span>

  - <span data-ttu-id="b0660-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="b0660-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="b0660-205">在所有包含超過10個專案的層中，會顯示前10個專案，而其餘專案則會結合在**其他**專案中。</span><span class="sxs-lookup"><span data-stu-id="b0660-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="b0660-206">URL 點選</span><span class="sxs-lookup"><span data-stu-id="b0660-206">URL clicks</span></span>

<span data-ttu-id="b0660-207">當網路釣魚郵件傳送至收件匣或 [垃圾郵件] 資料夾時，使用者永遠都有可能會按一下 [負載 URL]。</span><span class="sxs-lookup"><span data-stu-id="b0660-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="b0660-208">未在傳送的郵件中按一下 URL 只是一項成功的衡量，但是您必須決定網路釣魚郵件在第一個位置中傳遞到其信箱的原因。</span><span class="sxs-lookup"><span data-stu-id="b0660-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="b0660-209">如果使用者按一下網路釣魚郵件中的 [負載 URL]，則動作會顯示在 [市場活動詳細資料] 視圖中圖表的 [ **URL 按一下**] 區域中。</span><span class="sxs-lookup"><span data-stu-id="b0660-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="b0660-210">**允許**</span><span class="sxs-lookup"><span data-stu-id="b0660-210">**Allowed**</span></span>

- <span data-ttu-id="b0660-211">**BlockPage**：收件者已按一下有效載荷 URL，但組織中的[ATP 安全連結](atp-safe-links.md)原則已封鎖他們對惡意網站的存取。</span><span class="sxs-lookup"><span data-stu-id="b0660-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="b0660-212">**BlockPageOverride**：收件者按一下了郵件中的 [負載 URL]，ATP 安全連結嘗試停止它們，但允許他們覆寫區塊。</span><span class="sxs-lookup"><span data-stu-id="b0660-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="b0660-213">您必須調查您的[安全連結原則](set-up-atp-safe-links-policies.md)，以瞭解使用者為何可以覆寫安全連結判定，並繼續進行惡意網站。</span><span class="sxs-lookup"><span data-stu-id="b0660-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="b0660-214">**PendingDetonationPage**： ATP 安全附件正在虛擬電腦環境中開啟的負載 URL，並查看發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="b0660-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="b0660-215">**PendingDetonationPageOverride**：收件者可以覆寫 [負載引爆] 處理常式，並開啟 URL，而不會等候結果。</span><span class="sxs-lookup"><span data-stu-id="b0660-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="b0660-216">索引標籤</span><span class="sxs-lookup"><span data-stu-id="b0660-216">Tabs</span></span>

<span data-ttu-id="b0660-217">行銷活動詳細資料檢視中有數個索引標籤，可讓您進一步調查行銷活動。</span><span class="sxs-lookup"><span data-stu-id="b0660-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="b0660-218">**URL 按一下**：如果使用者未按一下網路釣魚郵件中的 [負載 URL]，此區段將會是空白的。</span><span class="sxs-lookup"><span data-stu-id="b0660-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="b0660-219">如果使用者能夠按一下 URL，則會填入下列值：</span><span class="sxs-lookup"><span data-stu-id="b0660-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="b0660-220">**使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b0660-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="b0660-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b0660-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="b0660-222">**點選時間**</span><span class="sxs-lookup"><span data-stu-id="b0660-222">**Click Time**</span></span>

  - <span data-ttu-id="b0660-223">**點選動作**</span><span class="sxs-lookup"><span data-stu-id="b0660-223">**Click Action**</span></span>

- <span data-ttu-id="b0660-224">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="b0660-224">**Sender IPs**</span></span>

  - <span data-ttu-id="b0660-225">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b0660-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="b0660-226">**總數**</span><span class="sxs-lookup"><span data-stu-id="b0660-226">**Total Count**</span></span>

  - <span data-ttu-id="b0660-227">**收件匣計數**</span><span class="sxs-lookup"><span data-stu-id="b0660-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="b0660-228">**封鎖的計數**</span><span class="sxs-lookup"><span data-stu-id="b0660-228">**Blocked Count**</span></span>

  - <span data-ttu-id="b0660-229">已**傳遞 SPF**：寄件者[原則架構（SPF）](how-office-365-uses-spf-to-prevent-spoofing.md)已驗證寄件者。</span><span class="sxs-lookup"><span data-stu-id="b0660-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="b0660-230">未通過 SPF 驗證的寄件者表示寄件者未驗證，或郵件哄騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="b0660-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="b0660-231">**寄件者**</span><span class="sxs-lookup"><span data-stu-id="b0660-231">**Senders**</span></span>

  - <span data-ttu-id="b0660-232">**寄件者**：這是 SMTP MAIL FROM 命令中的實際寄件者位址，不一定是使用者在其電子郵件客戶程式中看到的寄件者：電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b0660-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="b0660-233">**總數**</span><span class="sxs-lookup"><span data-stu-id="b0660-233">**Total Count**</span></span>

  - <span data-ttu-id="b0660-234">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="b0660-234">**Inboxed**</span></span>

  - <span data-ttu-id="b0660-235">**非 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="b0660-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="b0660-236">**DKIM 通過**：寄件者是由[識別為郵件（DKIM）的網域金鑰](support-for-validation-of-dkim-signed-messages.md)所驗證。</span><span class="sxs-lookup"><span data-stu-id="b0660-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="b0660-237">未通過 DKIM 驗證的寄件者會指出未驗證寄件者，或郵件會哄騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="b0660-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="b0660-238">**DMARC 通過**：寄件者是透過以[網域為基礎的郵件驗證、報告和符合性（DMARC）](use-dmarc-to-validate-email.md)進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b0660-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="b0660-239">未通過 DMARC 驗證的寄件者會指出未驗證寄件者，或郵件會哄騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="b0660-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="b0660-240">**承載**</span><span class="sxs-lookup"><span data-stu-id="b0660-240">**Payloads**</span></span>

  - <span data-ttu-id="b0660-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b0660-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="b0660-242">**總數**</span><span class="sxs-lookup"><span data-stu-id="b0660-242">**Total Count**</span></span>

<span data-ttu-id="b0660-243"><sup>\*</sup> 按一下此值會開啟新的飛出畫面，其中在行銷活動詳細資料檢視上方包含更多有關指定項目 (使用者、URL 等) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b0660-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="b0660-244">若要回到行銷活動詳細資料檢視，請按一下新飛出視窗中的 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0660-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="b0660-245">按鈕</span><span class="sxs-lookup"><span data-stu-id="b0660-245">Buttons</span></span>

<span data-ttu-id="b0660-246">行銷活動詳細資料檢視中的按鈕可讓您使用威脅瀏覽器的強大功能，進一步調查行銷活動。</span><span class="sxs-lookup"><span data-stu-id="b0660-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="b0660-247">**探索行銷活動**：使用 [行銷活動識別碼]\*\*\*\* 值做為搜尋篩選，以開啟新的威脅總管搜尋索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b0660-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="b0660-248">**探索 Inboxed 郵件**：開啟新的威脅瀏覽器搜尋索引標籤，使用**活動識別碼**及**傳遞位置：收件**匣做為搜尋篩選器。</span><span class="sxs-lookup"><span data-stu-id="b0660-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
