---
title: Office 365 ATP 中的行銷活動檢視
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
ms.openlocfilehash: 350f4f9007bf6f09836080af65802a9757532dcc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083536"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="6631f-103">Office 365 ATP 中的行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="6631f-103">Campaign Views in Office 365 ATP</span></span>

<span data-ttu-id="6631f-104">行銷活動檢視是 Office 365 安全性與合規性中心中進階威脅防護 (ATP) 的一項功能，可識別和分類服務中的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="6631f-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="6631f-105">行銷活動檢視可協助您：</span><span class="sxs-lookup"><span data-stu-id="6631f-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="6631f-106">更有效率地調查和回應網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="6631f-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="6631f-107">更進一步了解攻擊範圍。</span><span class="sxs-lookup"><span data-stu-id="6631f-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="6631f-108">向決策者展現價值。</span><span class="sxs-lookup"><span data-stu-id="6631f-108">Show value to decision makers.</span></span>

<span data-ttu-id="6631f-109">行銷活動檢視可讓您較任何人類所能夠，更快速且更完整地查看攻擊的全貌。</span><span class="sxs-lookup"><span data-stu-id="6631f-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="6631f-110">什麼是行銷活動？</span><span class="sxs-lookup"><span data-stu-id="6631f-110">What is a campaign?</span></span>

<span data-ttu-id="6631f-111">行銷活動是針對一或多個組織的協調式電子郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="6631f-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="6631f-112">竊取認證，以及公司資料的電子郵件攻擊所使用的重大和是業界。</span><span class="sxs-lookup"><span data-stu-id="6631f-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="6631f-113">技術增加以停止攻擊，攻擊者會在以確保後續的成效心力中修改它們的方法。</span><span class="sxs-lookup"><span data-stu-id="6631f-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="6631f-114">Microsoft 會跨整個 Office 365 服務以協助識別行銷活動運用大量反網路釣魚、 反垃圾郵件和反惡意程式碼的資料。</span><span class="sxs-lookup"><span data-stu-id="6631f-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire Office 365 service to help identify campaigns.</span></span> <span data-ttu-id="6631f-115">我們分析和分類根據幾個因素的攻擊資訊。</span><span class="sxs-lookup"><span data-stu-id="6631f-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="6631f-116">例如：</span><span class="sxs-lookup"><span data-stu-id="6631f-116">For example:</span></span>

- <span data-ttu-id="6631f-117">**攻擊來源**：來源 IP 位址和寄件者電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="6631f-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="6631f-118">**攻擊訊息屬性**：攻擊訊息的內容、樣式和調性。</span><span class="sxs-lookup"><span data-stu-id="6631f-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="6631f-119">**攻擊收件者**：收件者網域、收件者工作職掌 (系統管理員、執行人員等)、公司類型 (大型、小型、公有、私人等等) 以及產業。</span><span class="sxs-lookup"><span data-stu-id="6631f-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="6631f-120">**攻擊裝載**： 惡意連結、 附件，或是其他酬攻擊郵件中的。</span><span class="sxs-lookup"><span data-stu-id="6631f-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="6631f-121">行銷活動可能會短暫，或可能跨越幾天、 週或月與作用中且非使用中的期間。</span><span class="sxs-lookup"><span data-stu-id="6631f-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="6631f-122">行銷活動可能會啟動對您的特定部署組織或組織可能會跨多個公司的較大的行銷活動的一部分。</span><span class="sxs-lookup"><span data-stu-id="6631f-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="6631f-123">Office 365 安全性與合規性中心行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="6631f-123">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="6631f-124">**威脅管理，** 在[安全性 & 合規性中心](https://protection.office.com)活動檢視有\>**行銷活動**。</span><span class="sxs-lookup"><span data-stu-id="6631f-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![安全性與合規性中心的行銷活動概觀](../../media/campaigns-overview.png)

<span data-ttu-id="6631f-126">您也可以前往從行銷活動檢視：</span><span class="sxs-lookup"><span data-stu-id="6631f-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="6631f-127">**威脅管理，** \> **Explorer** \> **檢視** \> **行銷活動**</span><span class="sxs-lookup"><span data-stu-id="6631f-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="6631f-128">**威脅管理，** \> **Explorer** \> **檢視** \> **所有電子郵件** \> **活動**</span><span class="sxs-lookup"><span data-stu-id="6631f-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="6631f-129">如果您沒有看到任何行銷活動資料，請嘗試變更日期範圍。</span><span class="sxs-lookup"><span data-stu-id="6631f-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="6631f-130">概觀頁面會顯示有關行銷活動的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="6631f-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="6631f-131">**名稱**</span><span class="sxs-lookup"><span data-stu-id="6631f-131">**Name**</span></span>

- <span data-ttu-id="6631f-132">**樣本主旨**：行銷活動中其中一個訊息的主旨列。</span><span class="sxs-lookup"><span data-stu-id="6631f-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="6631f-133">請注意，活動中的所有郵件將不一定都有相同的主旨。</span><span class="sxs-lookup"><span data-stu-id="6631f-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="6631f-134">**類型**： 目前，此值永遠為**釣魚程式**。</span><span class="sxs-lookup"><span data-stu-id="6631f-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="6631f-135">**子類型**：本行銷活動要網路釣魚的品牌 (如適用)。</span><span class="sxs-lookup"><span data-stu-id="6631f-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="6631f-136">當偵測由 ATP 技術驅動時，前置詞**ATP-** 新增至子類型值。</span><span class="sxs-lookup"><span data-stu-id="6631f-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="6631f-137">**收件者**：此行銷活動鎖定的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="6631f-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="6631f-138">**Inboxed**： 從這個活動 （未傳遞至垃圾郵件） 其收件匣中收到郵件的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="6631f-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="6631f-139">**Clicked**： 網路釣魚郵件中的 URL 按下的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="6631f-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="6631f-140">**按一下 [率**： 百分比計算中的 「**Clicked** / **Inboxed**」。</span><span class="sxs-lookup"><span data-stu-id="6631f-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="6631f-141">這個值是為活動的有效性的指標，且是否收件者能夠識別為網路釣魚郵件，並避免按一下承載 URL。</span><span class="sxs-lookup"><span data-stu-id="6631f-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="6631f-142">**瀏覽過**： 多少使用者實際對它透過裝載網站。</span><span class="sxs-lookup"><span data-stu-id="6631f-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="6631f-143">如果有**Clicked**值，但安全連結封鎖對網站的存取，這個值會是零。</span><span class="sxs-lookup"><span data-stu-id="6631f-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="6631f-144">當您按一下行銷活動的名稱時，行銷活動詳細資料會顯示在飛出視窗中。</span><span class="sxs-lookup"><span data-stu-id="6631f-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="6631f-145">行銷活動詳細資料</span><span class="sxs-lookup"><span data-stu-id="6631f-145">Campaign details</span></span>

<span data-ttu-id="6631f-146">在行銷活動詳細資料檢視中，提供有關行銷活動的許多資訊：</span><span class="sxs-lookup"><span data-stu-id="6631f-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="6631f-147">行銷活動資訊：</span><span class="sxs-lookup"><span data-stu-id="6631f-147">Campaign information:</span></span>

  - <span data-ttu-id="6631f-148">**識別碼**： 唯一活動識別碼。</span><span class="sxs-lookup"><span data-stu-id="6631f-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="6631f-149">**開始**和**結束**：您選取的日期範圍篩選。</span><span class="sxs-lookup"><span data-stu-id="6631f-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="6631f-150">**影響**： 日期範圍內的下列資料篩選您選取：</span><span class="sxs-lookup"><span data-stu-id="6631f-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="6631f-151">收件者總數。</span><span class="sxs-lookup"><span data-stu-id="6631f-151">The total number of recipients.</span></span>

    - <span data-ttu-id="6631f-152">「 Inboxed 」 （也就，傳遞至收件匣，不適用於垃圾） 的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="6631f-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="6631f-153">多少使用者按一下 [網路釣魚郵件中的 URL 裝載。</span><span class="sxs-lookup"><span data-stu-id="6631f-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="6631f-154">Howe 許多使用者造訪 URL。</span><span class="sxs-lookup"><span data-stu-id="6631f-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="6631f-155">行銷活動時間表：行銷活動的開始和結束時間，以及一段時間內的訊息量。</span><span class="sxs-lookup"><span data-stu-id="6631f-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="6631f-156">行銷活動流程</span><span class="sxs-lookup"><span data-stu-id="6631f-156">Campaign flow</span></span>

<span data-ttu-id="6631f-157">有關行銷活動的重要詳細資料，會在 [流程]\*\*\*\* 區段中的水平流程圖 (稱為 _Sankey_ 圖表) 中顯示。</span><span class="sxs-lookup"><span data-stu-id="6631f-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="6631f-158">這些詳細資料將協助您了解行銷活動的元素和在組織中的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="6631f-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![未包含使用者 URL 點選的行銷活動詳細資料](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="6631f-160">如果您將游標停留在圖表中的水平帶狀上，您會看到相關訊息的數量 (例如來自特定來源 IP 的訊息、來自使用特定寄件者網域來源 IP 的訊息等)。</span><span class="sxs-lookup"><span data-stu-id="6631f-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="6631f-161">圖表中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="6631f-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="6631f-162">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="6631f-162">**Sender IPs**</span></span>

- <span data-ttu-id="6631f-163">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="6631f-163">**Sender domains**</span></span>

- <span data-ttu-id="6631f-164">**篩選結果**：此處的值與可用的防網路釣魚及反垃圾郵件篩選結果有關，如[反垃圾郵件訊息標頭](anti-spam-message-headers.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="6631f-164">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="6631f-165">下表說明可用的值：</span><span class="sxs-lookup"><span data-stu-id="6631f-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="6631f-166">值</span><span class="sxs-lookup"><span data-stu-id="6631f-166">Value</span></span>|<span data-ttu-id="6631f-167">垃圾郵件篩選器 verdict</span><span class="sxs-lookup"><span data-stu-id="6631f-167">Spam filter verdict</span></span>|<span data-ttu-id="6631f-168">描述</span><span class="sxs-lookup"><span data-stu-id="6631f-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="6631f-169">**允許**</span><span class="sxs-lookup"><span data-stu-id="6631f-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="6631f-170">郵件已標示為非垃圾郵件及 （或) 而略過篩選之前所評估的垃圾郵件篩選器 （例如，藉由郵件流程規則，也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="6631f-170">The message was marked as not spam and/or skipped filtering before being evaluated by the spam filter (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="6631f-171">郵件已略過垃圾郵件篩選因為其他原因 （例如，收件者與寄件者會出現在相同的組織）。</span><span class="sxs-lookup"><span data-stu-id="6631f-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="6631f-172">**已封鎖**</span><span class="sxs-lookup"><span data-stu-id="6631f-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="6631f-173">郵件已標示為垃圾郵件評估垃圾郵件篩選器之前 （例如，藉由郵件流程規則）。</span><span class="sxs-lookup"><span data-stu-id="6631f-173">The message was marked as spam before being evaluated by the spam filter (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="6631f-174">**已偵測**</span><span class="sxs-lookup"><span data-stu-id="6631f-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="6631f-175">郵件已標示為垃圾郵件的垃圾郵件篩選器。</span><span class="sxs-lookup"><span data-stu-id="6631f-175">The message was marked as spam by the spam filter.</span></span>|
  |<span data-ttu-id="6631f-176">**未偵測到**</span><span class="sxs-lookup"><span data-stu-id="6631f-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="6631f-177">郵件已標示為非垃圾郵件的垃圾郵件篩選器。</span><span class="sxs-lookup"><span data-stu-id="6631f-177">The message was marked as not spam by the spam filter.</span></span>|
  |<span data-ttu-id="6631f-178">**發行**</span><span class="sxs-lookup"><span data-stu-id="6631f-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="6631f-179">郵件已略過垃圾郵件篩選，因為它已從隔離釋放。</span><span class="sxs-lookup"><span data-stu-id="6631f-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="6631f-180">**租用戶允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6631f-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="6631f-181">郵件已略過垃圾郵件篩選由於垃圾郵件篩選原則設定 （例如，寄件者或網域已**寄件者允許**清單中）。</span><span class="sxs-lookup"><span data-stu-id="6631f-181">The message skipped spam filtering due to the spam filter policy configuration (for example, the sender or domain was in hte **Sender allow** list).</span></span>|
  |<span data-ttu-id="6631f-182">**租用戶區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="6631f-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="6631f-183">郵件已遭到垃圾郵件篩選由於垃圾郵件篩選原則設定 （例如，寄件者或網域的**寄件者封鎖**清單中）。</span><span class="sxs-lookup"><span data-stu-id="6631f-183">The message was blocked by spam filtering due to the spam filter policy configuration (for example, the sender or domain was in the **Sender block** list).</span></span>|
  |<span data-ttu-id="6631f-184">**允許使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6631f-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="6631f-185">郵件已略過垃圾郵件篩選，因為寄件者已在 Outlook 中的使用者的安全寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="6631f-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="6631f-186">**使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="6631f-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="6631f-187">垃圾郵件篩選，因為寄件者已在 Outlook 中的使用者的封鎖寄件者清單中的已封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="6631f-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="6631f-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="6631f-188">**ZAP**</span></span>|<span data-ttu-id="6631f-189">n/a</span><span class="sxs-lookup"><span data-stu-id="6631f-189">n/a</span></span>|<span data-ttu-id="6631f-190">[零時差自動清除 (ZAP)](zero-hour-auto-purge.md)上傳送的郵件，根據您 （移至 [垃圾郵件] 資料夾或隔離） 的垃圾郵件篩選原則設定來執行巨集指令。</span><span class="sxs-lookup"><span data-stu-id="6631f-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your spam filter policy configuration (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="6631f-191"><sup>\*</sup>檢閱您垃圾郵件篩選器原則的組態設定，因為允許的郵件會有可能被封鎖服務。</span><span class="sxs-lookup"><span data-stu-id="6631f-191"><sup>\*</sup> Review your spam filter policy configuration settings, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="6631f-192"><sup>\*\*</sup>檢閱您垃圾郵件篩選器原則的組態設定，因為這些郵件應該隔離，未傳遞。</span><span class="sxs-lookup"><span data-stu-id="6631f-192"><sup>\*\*</sup> Review your spam filter policy configuration settings, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="6631f-193">**傳送位置**：您可能想要調查實際傳送給收件者的訊息 (無論是移至 [收件匣] 或 [垃圾郵件] 資料夾)，即使使用者未在訊息中點選承載 URL。</span><span class="sxs-lookup"><span data-stu-id="6631f-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="6631f-194">您也可以移除被隔離的郵件從隔離區。</span><span class="sxs-lookup"><span data-stu-id="6631f-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="6631f-195">如需詳細資訊，請參閱[在 Office 365 中隔離電子郵件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="6631f-195">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="6631f-196">**已刪除資料夾**</span><span class="sxs-lookup"><span data-stu-id="6631f-196">**Deleted folder**</span></span>

  - <span data-ttu-id="6631f-197">**捨棄**</span><span class="sxs-lookup"><span data-stu-id="6631f-197">**Dropped**</span></span>

  - <span data-ttu-id="6631f-198">**外部**： 收件者位於您內部部署電子郵件組織。</span><span class="sxs-lookup"><span data-stu-id="6631f-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="6631f-199">**失敗**</span><span class="sxs-lookup"><span data-stu-id="6631f-199">**Failed**</span></span>

  - <span data-ttu-id="6631f-200">**轉寄**</span><span class="sxs-lookup"><span data-stu-id="6631f-200">**Forwarded**</span></span>

  - <span data-ttu-id="6631f-201">**收件匣**</span><span class="sxs-lookup"><span data-stu-id="6631f-201">**Inbox**</span></span>

  - <span data-ttu-id="6631f-202">**垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="6631f-202">**Junk folder**</span></span>

  - <span data-ttu-id="6631f-203">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="6631f-203">**Quarantine**</span></span>

  - <span data-ttu-id="6631f-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="6631f-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="6631f-205">在包含超過 10 個項目之所有圖層，會顯示的前 10 項，而其餘部分會一起在**其他**所示。</span><span class="sxs-lookup"><span data-stu-id="6631f-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="6631f-206">URL 點選</span><span class="sxs-lookup"><span data-stu-id="6631f-206">URL clicks</span></span>

<span data-ttu-id="6631f-207">當網路釣魚郵件會傳遞至收件者 （收件匣] 或 [垃圾郵件資料夾） 時，一定會有使用者可按一下承載 URL 的機率。</span><span class="sxs-lookup"><span data-stu-id="6631f-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="6631f-208">不按一下傳送的郵件中的 URL 是小型量值的成功，但是您必須決定為什麼網路釣魚郵件已傳遞至他們的信箱在第一時間。</span><span class="sxs-lookup"><span data-stu-id="6631f-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="6631f-209">如果使用者按一下 [網路釣魚郵件中的承載 URL，動作會顯示在**按一下 [URL** ] 區域中的活動詳細資料] 檢視中的圖表。</span><span class="sxs-lookup"><span data-stu-id="6631f-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="6631f-210">**允許**</span><span class="sxs-lookup"><span data-stu-id="6631f-210">**Allowed**</span></span>

- <span data-ttu-id="6631f-211">**BlockPage**： 在承載 URL] 中，按一下 [收件者，但惡意網站存取已封鎖您組織中的[ATP 安全連結](atp-safe-links.md)原則。</span><span class="sxs-lookup"><span data-stu-id="6631f-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="6631f-212">**BlockPageOverride**： 收件者按一下 [在郵件中，嘗試將它們，停止的 ATP 安全連結的承載 URL，但他們已允許覆寫封鎖。</span><span class="sxs-lookup"><span data-stu-id="6631f-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="6631f-213">您需要調查您若要查看為什麼允許使用者覆寫 [安全連結 verdict，並繼續惡意網站的[安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6631f-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="6631f-214">**PendingDetonationPage**： 在虛擬電腦環境中，開啟承載 URL 正在 ATP 安全附件和看到什麼情況。</span><span class="sxs-lookup"><span data-stu-id="6631f-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="6631f-215">**PendingDetonationPageOverride**： 收件者已允許覆寫承載爆炸程序，並開啟 URL，而不需等待的結果。</span><span class="sxs-lookup"><span data-stu-id="6631f-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="6631f-216">索引標籤</span><span class="sxs-lookup"><span data-stu-id="6631f-216">Tabs</span></span>

<span data-ttu-id="6631f-217">行銷活動詳細資料檢視中有數個索引標籤，可讓您進一步調查行銷活動。</span><span class="sxs-lookup"><span data-stu-id="6631f-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="6631f-218">**按一下 [URL**： 如果使用者未按一下網路釣魚郵件中的承載 URL，這一節將為空白。</span><span class="sxs-lookup"><span data-stu-id="6631f-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="6631f-219">如果使用者能夠在 URL 上按一下 [，便會填入下列值：</span><span class="sxs-lookup"><span data-stu-id="6631f-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="6631f-220">**使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6631f-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="6631f-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6631f-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="6631f-222">**點選時間**</span><span class="sxs-lookup"><span data-stu-id="6631f-222">**Click Time**</span></span>

  - <span data-ttu-id="6631f-223">**點選動作**</span><span class="sxs-lookup"><span data-stu-id="6631f-223">**Click Action**</span></span>

- <span data-ttu-id="6631f-224">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="6631f-224">**Sender IPs**</span></span>

  - <span data-ttu-id="6631f-225">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6631f-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="6631f-226">**總數**</span><span class="sxs-lookup"><span data-stu-id="6631f-226">**Total Count**</span></span>

  - <span data-ttu-id="6631f-227">**收件匣計數**</span><span class="sxs-lookup"><span data-stu-id="6631f-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="6631f-228">**封鎖的計數**</span><span class="sxs-lookup"><span data-stu-id="6631f-228">**Blocked Count**</span></span>

  - <span data-ttu-id="6631f-229">**SPF 傳遞**： 寄件者已驗證的[寄件者原則架構 (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="6631f-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="6631f-230">未通過 SPF 驗證寄件者指出寄件者未通過驗證，或郵件詐騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="6631f-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="6631f-231">**寄件者**</span><span class="sxs-lookup"><span data-stu-id="6631f-231">**Senders**</span></span>

  - <span data-ttu-id="6631f-232">**寄件者**： 這是在 SMTP MAIL FROM 命令中，而不一定是 [從實際寄件者地址： 電子郵件使用者在其電子郵件用戶端中看到的地址。</span><span class="sxs-lookup"><span data-stu-id="6631f-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="6631f-233">**總數**</span><span class="sxs-lookup"><span data-stu-id="6631f-233">**Total Count**</span></span>

  - <span data-ttu-id="6631f-234">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="6631f-234">**Inboxed**</span></span>

  - <span data-ttu-id="6631f-235">**不 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="6631f-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="6631f-236">**DKIM 傳遞**： 寄件者已驗證的[網域金鑰 Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="6631f-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="6631f-237">未通過 DKIM 驗證寄件者指出寄件者未通過驗證，或郵件詐騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="6631f-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="6631f-238">**DMARC 傳遞**： 寄件者已驗證的[網域為基礎的郵件驗證、 報告和符合性聲明 (DMARC)](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="6631f-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="6631f-239">未通過 DMARC 驗證寄件者指出寄件者未通過驗證，或郵件詐騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="6631f-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="6631f-240">**承載**</span><span class="sxs-lookup"><span data-stu-id="6631f-240">**Payloads**</span></span>

  - <span data-ttu-id="6631f-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6631f-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="6631f-242">**總數**</span><span class="sxs-lookup"><span data-stu-id="6631f-242">**Total Count**</span></span>

<span data-ttu-id="6631f-243"><sup>\*</sup> 按一下此值會開啟新的飛出畫面，其中在行銷活動詳細資料檢視上方包含更多有關指定項目 (使用者、URL 等) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6631f-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="6631f-244">若要回到行銷活動詳細資料檢視，請按一下新飛出視窗中的 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6631f-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="6631f-245">按鈕</span><span class="sxs-lookup"><span data-stu-id="6631f-245">Buttons</span></span>

<span data-ttu-id="6631f-246">行銷活動詳細資料檢視中的按鈕可讓您使用威脅瀏覽器的強大功能，進一步調查行銷活動。</span><span class="sxs-lookup"><span data-stu-id="6631f-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="6631f-247">**探索行銷活動**：使用 [行銷活動識別碼]\*\*\*\* 值做為搜尋篩選，以開啟新的威脅總管搜尋索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6631f-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="6631f-248">**瀏覽 Inboxed 郵件**： 開啟新威脅總管搜尋] 索引標籤上使用 **「 活動識別碼**和**傳遞位置： 收件匣**作為搜尋篩選器。</span><span class="sxs-lookup"><span data-stu-id="6631f-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
