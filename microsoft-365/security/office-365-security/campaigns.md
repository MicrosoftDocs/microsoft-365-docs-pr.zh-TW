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
ms.openlocfilehash: 65ae346fc4ffdcc502c7f479d7d92753cdb5b5bc
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599760"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="8593a-103">Office 365 ATP 中的行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="8593a-103">Campaign Views in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="8593a-104">本主題中所述的功能目前處於預覽，且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="8593a-104">The features described in this topic are currently in preview, and are subject to change.</span></span>

<span data-ttu-id="8593a-105">行銷活動檢視是 Office 365 安全性與合規性中心中進階威脅防護 (ATP) 的一項功能，可識別和分類服務中的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="8593a-105">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="8593a-106">行銷活動檢視可協助您：</span><span class="sxs-lookup"><span data-stu-id="8593a-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="8593a-107">更有效率地調查和回應網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="8593a-107">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="8593a-108">更進一步了解攻擊範圍。</span><span class="sxs-lookup"><span data-stu-id="8593a-108">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="8593a-109">向決策者展現價值。</span><span class="sxs-lookup"><span data-stu-id="8593a-109">Show value to decision makers.</span></span>

<span data-ttu-id="8593a-110">行銷活動檢視可讓您較任何人類所能夠，更快速且更完整地查看攻擊的全貌。</span><span class="sxs-lookup"><span data-stu-id="8593a-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="8593a-111">什麼是行銷活動？</span><span class="sxs-lookup"><span data-stu-id="8593a-111">What is a campaign?</span></span>

<span data-ttu-id="8593a-112">行銷活動是針對一或多個組織的協調式電子郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="8593a-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="8593a-113">現今，竊取認證和公司資料的電子郵件攻擊是一項龐大且能賺錢的生意。</span><span class="sxs-lookup"><span data-stu-id="8593a-113">Today, email attacks that steal credentials and company data are a big and lucrative business.</span></span> <span data-ttu-id="8593a-114">隨著為了阻擋攻擊的技術增加，攻擊者更為老練而足以修改其方法，以確保持續成功。</span><span class="sxs-lookup"><span data-stu-id="8593a-114">As technologies increase in an effort to stop attacks, attackers are sophisticated enough to modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="8593a-115">Microsoft 利用大量防網路釣魚、反垃圾郵件和反惡意程式碼資料，以及在全球各地的整個 Office 365 服務的經驗，以找出行銷活動。</span><span class="sxs-lookup"><span data-stu-id="8593a-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data and experience across the entire Office 365 service world-wide to identify campaigns.</span></span> <span data-ttu-id="8593a-116">系統會根據數個因素分析和分類攻擊資訊。</span><span class="sxs-lookup"><span data-stu-id="8593a-116">The attack information is analyzed and classified according to several factors.</span></span> <span data-ttu-id="8593a-117">例如：</span><span class="sxs-lookup"><span data-stu-id="8593a-117">For example:</span></span>

- <span data-ttu-id="8593a-118">**攻擊來源**：來源 IP 位址和寄件者電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="8593a-118">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="8593a-119">**攻擊訊息屬性**：攻擊訊息的內容、樣式和調性。</span><span class="sxs-lookup"><span data-stu-id="8593a-119">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="8593a-120">**攻擊收件者**：收件者網域、收件者工作職掌 (系統管理員、執行人員等)、公司類型 (大型、小型、公有、私人等等) 以及產業。</span><span class="sxs-lookup"><span data-stu-id="8593a-120">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="8593a-121">**攻擊承載**：惡意連結、附件或其他承載。</span><span class="sxs-lookup"><span data-stu-id="8593a-121">**Attack payload**: Malicious links, attachments, or other payloads.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="8593a-122">Office 365 安全性與合規性中心行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="8593a-122">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="8593a-123">您可以在下列位置的[安全性與合規性中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中取得行銷活動檢視：</span><span class="sxs-lookup"><span data-stu-id="8593a-123">Campaign Views is available in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) at the following locations:</span></span>

- <span data-ttu-id="8593a-124">**威脅管理** \> **總管** \> **檢視** \> **網路釣魚** \> **熱門活動 (預覽)**</span><span class="sxs-lookup"><span data-stu-id="8593a-124">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Top campaign (Preview)**</span></span>

- <span data-ttu-id="8593a-125">**威脅管理** \> **總管** \> **檢視** \> **所有電子郵件** \> **熱門活動 (預覽)**</span><span class="sxs-lookup"><span data-stu-id="8593a-125">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Top campaign (Preview)**</span></span>

![安全性與合規性中心的行銷活動概觀](../media/campaigns-overview.png)

> [!TIP]
> <span data-ttu-id="8593a-127">目前唯一可用的篩選是日期範圍。</span><span class="sxs-lookup"><span data-stu-id="8593a-127">Currently, the only filtering that's available is the date range.</span></span> <span data-ttu-id="8593a-128">如果您沒有看到任何行銷活動資料，請嘗試變更日期範圍。</span><span class="sxs-lookup"><span data-stu-id="8593a-128">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="8593a-129">概觀頁面會顯示有關行銷活動的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="8593a-129">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="8593a-130">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8593a-130">**Name**</span></span>

- <span data-ttu-id="8593a-131">**樣本主旨**：行銷活動中其中一個訊息的主旨列。</span><span class="sxs-lookup"><span data-stu-id="8593a-131">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="8593a-132">請注意，並非行銷活動中的_所有_訊息都會有這個相同的主旨列。</span><span class="sxs-lookup"><span data-stu-id="8593a-132">Note that _all_ the messages in the campaign will not necessarily have this same subject line.</span></span>

- <span data-ttu-id="8593a-133">**類型**：目前此值將一律是**網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="8593a-133">**Type**: Currently, this value will always be **Phish**.</span></span>

- <span data-ttu-id="8593a-134">**子類型**：本行銷活動要網路釣魚的品牌 (如適用)。</span><span class="sxs-lookup"><span data-stu-id="8593a-134">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="8593a-135">當偵測是由 ATP 技術驅動時，系統會在子類型值中新增字首 **ATP-**。</span><span class="sxs-lookup"><span data-stu-id="8593a-135">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="8593a-136">**收件者**：此行銷活動鎖定的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="8593a-136">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="8593a-137">**已傳送**：在其收件匣中收到來自此行銷活動訊息的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="8593a-137">**Delivered**: The number of users that received messages from this campaign into their Inbox.</span></span>

- <span data-ttu-id="8593a-138">**ID**：行銷活動的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="8593a-138">**ID**: A unique identifier for the campaign.</span></span>

<span data-ttu-id="8593a-139">當您按一下行銷活動的名稱時，行銷活動詳細資料會顯示在飛出視窗中。</span><span class="sxs-lookup"><span data-stu-id="8593a-139">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="8593a-140">行銷活動詳細資料</span><span class="sxs-lookup"><span data-stu-id="8593a-140">Campaign details</span></span>

<span data-ttu-id="8593a-141">在行銷活動詳細資料檢視中，提供有關行銷活動的許多資訊：</span><span class="sxs-lookup"><span data-stu-id="8593a-141">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="8593a-142">行銷活動資訊：</span><span class="sxs-lookup"><span data-stu-id="8593a-142">Campaign information:</span></span>

  - <span data-ttu-id="8593a-143">**識別碼**：與概觀畫面的行銷活動相同的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="8593a-143">**ID**: The same unique identifier of the campaign from the overview screen.</span></span>

  - <span data-ttu-id="8593a-144">**開始**和**結束**：您選取的日期範圍篩選。</span><span class="sxs-lookup"><span data-stu-id="8593a-144">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="8593a-145">**影響**：在您選取的日期範圍中傳送的訊息數量、「加入收件匣」(也就是傳送到收件匣) 的數量，以及有多少個使用者在網路釣魚訊息中的 URL 承載上點選。</span><span class="sxs-lookup"><span data-stu-id="8593a-145">**Impact**: the number of messages sent in the date range you selected, how many were "inboxed" (that is, delivered to the Inbox), and how many users clicked on the URL payload in the phishing message.</span></span>

  - <span data-ttu-id="8593a-146">行銷活動時間表：行銷活動的開始和結束時間，以及一段時間內的訊息量。</span><span class="sxs-lookup"><span data-stu-id="8593a-146">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="8593a-147">行銷活動流程</span><span class="sxs-lookup"><span data-stu-id="8593a-147">Campaign flow</span></span>

<span data-ttu-id="8593a-148">有關行銷活動的重要詳細資料，會在 [流程]\*\*\*\* 區段中的水平流程圖 (稱為 _Sankey_ 圖表) 中顯示。</span><span class="sxs-lookup"><span data-stu-id="8593a-148">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="8593a-149">這些詳細資料將協助您了解行銷活動的元素和在組織中的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="8593a-149">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![未包含使用者 URL 點選的行銷活動詳細資料](../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="8593a-151">如果您將游標停留在圖表中的水平帶狀上，您會看到相關訊息的數量 (例如來自特定來源 IP 的訊息、來自使用特定寄件者網域來源 IP 的訊息等)。</span><span class="sxs-lookup"><span data-stu-id="8593a-151">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="8593a-152">圖表中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="8593a-152">The diagram contains the following information:</span></span>

- <span data-ttu-id="8593a-153">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="8593a-153">**Sender IPs**</span></span>

- <span data-ttu-id="8593a-154">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="8593a-154">**Sender domains**</span></span>

- <span data-ttu-id="8593a-155">**篩選結果**：此處的值與可用的防網路釣魚及反垃圾郵件篩選結果有關，如[反垃圾郵件訊息標頭](anti-spam-message-headers.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="8593a-155">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="8593a-156">此處最有意思的是**租用戶允許**值，這表示組織中進行的設定會允許可能已由服務封鎖的訊息 (例如 [允許的寄件者] 清單中的網域)。</span><span class="sxs-lookup"><span data-stu-id="8593a-156">Of great interest here are the values **Tenant Allow**, which means a configured setting in the organization allowed a message through that would have been otherwise blocked by the service (for example, a domain in the Allowed Senders list).</span></span>

  - <span data-ttu-id="8593a-157">**租用戶封鎖**：此值表示組織中的某個設定 (例如，[封鎖的寄件者](create-block-sender-lists-in-office-365.md)清單中的網域項目) 會同時偵測訊息並判斷傳送該訊息的位置。</span><span class="sxs-lookup"><span data-stu-id="8593a-157">**Tenant Block**: This value indicates that a setting in your organization (for example, a domain entry in the [Blocked Senders list](create-block-sender-lists-in-office-365.md)) both detected the message and determined where it was delivered.</span></span> <span data-ttu-id="8593a-158">針對未隔離的訊息，請檢閱您的封鎖的寄件者設定，以判斷傳送訊息的原因。</span><span class="sxs-lookup"><span data-stu-id="8593a-158">For messages that weren't quarantined, review your blocked senders settings to determine why the message was delivered.</span></span>

  - <span data-ttu-id="8593a-159">**已偵測**</span><span class="sxs-lookup"><span data-stu-id="8593a-159">**Detected**</span></span>

  - <span data-ttu-id="8593a-160">**租用戶允許**</span><span class="sxs-lookup"><span data-stu-id="8593a-160">**Tenant Allow**</span></span>

- <span data-ttu-id="8593a-161">**傳送位置**：您可能想要調查實際傳送給收件者的訊息 (無論是移至 [收件匣] 或 [垃圾郵件] 資料夾)，即使使用者未在訊息中點選承載 URL。</span><span class="sxs-lookup"><span data-stu-id="8593a-161">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="8593a-162">您也可以透過[在 Office 365 中隔離電子郵件訊息](quarantine-email-messages.md)，來移除隔離的訊息。</span><span class="sxs-lookup"><span data-stu-id="8593a-162">You can also remove the quarantined messages from [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="8593a-163">**垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="8593a-163">**Junk folder**</span></span>

  - <span data-ttu-id="8593a-164">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="8593a-164">**Quarantine**</span></span>

  - <span data-ttu-id="8593a-165">**收件匣**</span><span class="sxs-lookup"><span data-stu-id="8593a-165">**Inbox**</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="8593a-166">URL 點選</span><span class="sxs-lookup"><span data-stu-id="8593a-166">URL clicks</span></span>

<span data-ttu-id="8593a-167">使用者總是有機會對傳送到收件者的 [收件匣] 或 [垃圾郵件] 資料夾中的訊息採取行動 (亦即，使用者將點選訊息中的惡意 URL)。</span><span class="sxs-lookup"><span data-stu-id="8593a-167">There's always the chance that messages delivered to the recipient's Inbox or Junk Email folder can be acted upon by the user (that is, user will click on the malicious URL in the message).</span></span> <span data-ttu-id="8593a-168">如果使用者沒有點選，這是極少程度的成功，不過您當然必須判斷為什麼最初將有害的訊息傳送至其信箱。</span><span class="sxs-lookup"><span data-stu-id="8593a-168">If they haven't, that's a small measure of success, although you certainly need to determine why the harmful message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="8593a-169">如果使用者已點選惡意的 URL，動作會顯示在圖表的 [URL 點選]\*\*\*\* 區域。</span><span class="sxs-lookup"><span data-stu-id="8593a-169">If a user has clicked on the malicious URL, the actions are displayed in the **URL clicks** area of the diagram.</span></span>

![包含使用者 URL 點選的行銷活動詳細資料](../media/campaign-details-with-recipient-actions.png)

- <span data-ttu-id="8593a-171">**安全連結封鎖**：此值表示收件者點選訊息中的承載 URL，但它已由組織中的 [ATP 安全連結](atp-safe-links.md) 原則封鎖。</span><span class="sxs-lookup"><span data-stu-id="8593a-171">**Safe Links Block**: This value indicates the recipient clicked on the payload URL in the message, but it was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="8593a-172">**安全連結封鎖覆寫**：此值也表示收件者已點選訊息中的承載 URL，而 [ATP 安全連結] 嘗試阻止這些連結，但它們已被允許覆寫封鎖。</span><span class="sxs-lookup"><span data-stu-id="8593a-172">**Safe Links Block Override**: This value also indicates the recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="8593a-173">您需要調查[安全連結原則](set-up-atp-safe-links-policies.md)，以查看為何允許使用者覆寫安全連結結果，並點選惡意 URL。</span><span class="sxs-lookup"><span data-stu-id="8593a-173">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and click on malicious URLs.</span></span>

### <a name="tabs"></a><span data-ttu-id="8593a-174">索引標籤</span><span class="sxs-lookup"><span data-stu-id="8593a-174">Tabs</span></span>

<span data-ttu-id="8593a-175">行銷活動詳細資料檢視中有數個索引標籤，可讓您進一步調查行銷活動。</span><span class="sxs-lookup"><span data-stu-id="8593a-175">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="8593a-176">**URL 點選**：如果沒有點選網路釣魚訊息中的承載 URL，則此區段會是空白。</span><span class="sxs-lookup"><span data-stu-id="8593a-176">**URL Clicks**: If the payload URL in the phishing message wasn't clicked, this section will be blank.</span></span> <span data-ttu-id="8593a-177">如果使用者可以點選 URL，您</span><span class="sxs-lookup"><span data-stu-id="8593a-177">If a user was able to click on the URL, you</span></span>

  - <span data-ttu-id="8593a-178">**使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8593a-178">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="8593a-179">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8593a-179">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="8593a-180">**點選時間**</span><span class="sxs-lookup"><span data-stu-id="8593a-180">**Click Time**</span></span>

  - <span data-ttu-id="8593a-181">**點選動作**</span><span class="sxs-lookup"><span data-stu-id="8593a-181">**Click Action**</span></span>

- <span data-ttu-id="8593a-182">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="8593a-182">**Sender IPs**</span></span>

  - <span data-ttu-id="8593a-183">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8593a-183">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="8593a-184">**總數**</span><span class="sxs-lookup"><span data-stu-id="8593a-184">**Total Count**</span></span>

  - <span data-ttu-id="8593a-185">**收件匣計數**</span><span class="sxs-lookup"><span data-stu-id="8593a-185">**Inboxed Count**</span></span>

  - <span data-ttu-id="8593a-186">**封鎖的計數**</span><span class="sxs-lookup"><span data-stu-id="8593a-186">**Blocked Count**</span></span>

  - <span data-ttu-id="8593a-187">**SPF 已通過**</span><span class="sxs-lookup"><span data-stu-id="8593a-187">**SPF Passed**</span></span>

- <span data-ttu-id="8593a-188">**寄件者**</span><span class="sxs-lookup"><span data-stu-id="8593a-188">**Senders**</span></span>

  - <span data-ttu-id="8593a-189">**寄件者**</span><span class="sxs-lookup"><span data-stu-id="8593a-189">**Sender**</span></span>

  - <span data-ttu-id="8593a-190">**總數**</span><span class="sxs-lookup"><span data-stu-id="8593a-190">**Total Count**</span></span>

  - <span data-ttu-id="8593a-191">**收件匣計數**</span><span class="sxs-lookup"><span data-stu-id="8593a-191">**Inboxed Count**</span></span>

  - <span data-ttu-id="8593a-192">**封鎖的計數**</span><span class="sxs-lookup"><span data-stu-id="8593a-192">**Blocked Count**</span></span>

  - <span data-ttu-id="8593a-193">**DKIM 已通過**</span><span class="sxs-lookup"><span data-stu-id="8593a-193">**DKIM Passed**</span></span>

  - <span data-ttu-id="8593a-194">**DMARC 已通過**</span><span class="sxs-lookup"><span data-stu-id="8593a-194">**DMARC Passed**</span></span>

- <span data-ttu-id="8593a-195">**承載**</span><span class="sxs-lookup"><span data-stu-id="8593a-195">**Payloads**</span></span>

  - <span data-ttu-id="8593a-196">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8593a-196">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="8593a-197">**總數**</span><span class="sxs-lookup"><span data-stu-id="8593a-197">**Total Count**</span></span>

<span data-ttu-id="8593a-198"><sup>\*</sup> 按一下此值會開啟新的飛出畫面，其中在行銷活動詳細資料檢視上方包含更多有關指定項目 (使用者、URL 等) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8593a-198"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="8593a-199">若要回到行銷活動詳細資料檢視，請按一下新飛出視窗中的 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8593a-199">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="8593a-200">按鈕</span><span class="sxs-lookup"><span data-stu-id="8593a-200">Buttons</span></span>

<span data-ttu-id="8593a-201">行銷活動詳細資料檢視中的按鈕可讓您使用威脅瀏覽器的強大功能，進一步調查行銷活動。</span><span class="sxs-lookup"><span data-stu-id="8593a-201">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="8593a-202">**探索行銷活動**：使用 [行銷活動識別碼]\*\*\*\* 值做為搜尋篩選，以開啟新的威脅總管搜尋索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8593a-202">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="8593a-203">**探索收件匣訊息**：使用 [行銷活動識別碼]\*\*\*\* 和 [傳送位置]\*\*\*\* 做為搜尋篩選，以開啟新的威脅總管搜尋索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8593a-203">**Explore Inbox messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
