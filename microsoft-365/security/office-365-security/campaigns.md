---
title: Office 365 ATP 方案中的即時檢視
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 了解 Office 365 進階威脅防護中的行銷活動檢視。
ms.openlocfilehash: 00af3f241bc1d9fd2cae9ebae0cdec7817679ed2
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430570"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="2af6c-103">Office 365 ATP 中的行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="2af6c-103">Campaign Views in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2af6c-104">[活動] 視圖是「高級威脅防護」中的一項功能， (ATP) Plan 2 (例如，Microsoft 365 E5 或具有 ATP Plan 2 附加元件) 的組織。</span><span class="sxs-lookup"><span data-stu-id="2af6c-104">Campaign Views is a feature in Advanced Threat Protection (ATP) Plan 2 (for example Microsoft 365 E5 or organizations with an ATP Plan 2 add-on).</span></span> <span data-ttu-id="2af6c-105">安全性 & 合規性中心的即時檢視會識別和分類服務中的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="2af6c-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="2af6c-106">行銷活動檢視可協助您：</span><span class="sxs-lookup"><span data-stu-id="2af6c-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="2af6c-107">更有效率地調查和回應網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="2af6c-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="2af6c-108">更進一步了解攻擊範圍。</span><span class="sxs-lookup"><span data-stu-id="2af6c-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="2af6c-109">向決策者展現價值。</span><span class="sxs-lookup"><span data-stu-id="2af6c-109">Show value to decision makers.</span></span>

<span data-ttu-id="2af6c-110">行銷活動檢視可讓您較任何人類所能夠，更快速且更完整地查看攻擊的全貌。</span><span class="sxs-lookup"><span data-stu-id="2af6c-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="2af6c-111">什麼是行銷活動？</span><span class="sxs-lookup"><span data-stu-id="2af6c-111">What is a campaign?</span></span>

<span data-ttu-id="2af6c-112">行銷活動是針對一或多個組織的協調式電子郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="2af6c-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="2af6c-113">竊取認證及公司資料的電子郵件攻擊是大型且 lucrative 的行業。</span><span class="sxs-lookup"><span data-stu-id="2af6c-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="2af6c-114">隨著技術不斷增加以停止攻擊的努力，攻擊者會修改其方法，以確保持續成功。</span><span class="sxs-lookup"><span data-stu-id="2af6c-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="2af6c-115">Microsoft 會利用整個服務中大量的反網路釣魚、反垃圾郵件和反惡意程式碼資料，協助識別市場活動。</span><span class="sxs-lookup"><span data-stu-id="2af6c-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="2af6c-116">我們會根據數個因素來分析和分類攻擊資訊。</span><span class="sxs-lookup"><span data-stu-id="2af6c-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="2af6c-117">例如：</span><span class="sxs-lookup"><span data-stu-id="2af6c-117">For example:</span></span>

- <span data-ttu-id="2af6c-118">**攻擊來源**：來源 IP 位址和寄件者電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="2af6c-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="2af6c-119">**郵件屬性**：郵件的內容、樣式和音調。</span><span class="sxs-lookup"><span data-stu-id="2af6c-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="2af6c-120">**郵件收件**者：收件者的關聯方式。</span><span class="sxs-lookup"><span data-stu-id="2af6c-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="2af6c-121">例如，收件者網域、收件者工作職能 (系統管理員、行政人員等 ) 、公司類型 (大型、small、public、private、private、) 及工業。</span><span class="sxs-lookup"><span data-stu-id="2af6c-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="2af6c-122">**攻擊負載**：郵件中的惡意連結、附件或其他負載。</span><span class="sxs-lookup"><span data-stu-id="2af6c-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="2af6c-123">市場活動可能會短期，或可能跨越數天、數周或數天，具有有效和非使用中的期間。</span><span class="sxs-lookup"><span data-stu-id="2af6c-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="2af6c-124">您的特定組織可能會發起一個市場活動，否則您的組織可能會是多個公司的較大活動的一部分。</span><span class="sxs-lookup"><span data-stu-id="2af6c-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="2af6c-125">安全性 & 規範中心內的即時檢視</span><span class="sxs-lookup"><span data-stu-id="2af6c-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="2af6c-126">在**威脅管理**活動的[安全性 & 規範中心](https://protection.office.com) \> \*\* \*\*，或是直接在中提供即時檢視 <https://protection.office.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="2af6c-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![安全性與合規性中心的行銷活動概觀](../../media/campaigns-overview.png)

<span data-ttu-id="2af6c-128">您也可以從下列來源取得市場即時檢視：</span><span class="sxs-lookup"><span data-stu-id="2af6c-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="2af6c-129">**威脅管理** \>**瀏覽器** \>**View** \>**活動**</span><span class="sxs-lookup"><span data-stu-id="2af6c-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="2af6c-130">**威脅管理** \>**瀏覽器** \>**View** \>**所有電子郵件** \>[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="2af6c-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="2af6c-131">**威脅管理** \>**瀏覽器** \>**View** \>**網路釣魚** \>[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="2af6c-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="2af6c-132">**威脅管理** \>**瀏覽器** \>**View** \>**惡意** \> 代碼[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="2af6c-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="2af6c-133">若要存取市場即時檢視，您必須是 Security & 合規性中心內的 **組織管理**、 **安全性管理員**或 **安全性讀者** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2af6c-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="2af6c-134">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2af6c-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="2af6c-135">市場活動概覽</span><span class="sxs-lookup"><span data-stu-id="2af6c-135">Campaigns overview</span></span>

<span data-ttu-id="2af6c-136">[一覽表] 頁面會顯示所有市場活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2af6c-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="2af6c-137">在 [預設 **市場活動** ] 索引標籤上，[ **行銷活動類型** ] 區域會顯示柱狀圖圖，顯示每日的收件者人數。</span><span class="sxs-lookup"><span data-stu-id="2af6c-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="2af6c-138">根據預設，圖表會顯示 **網路釣魚** 和 **惡意** 代碼資料。</span><span class="sxs-lookup"><span data-stu-id="2af6c-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="2af6c-139">如果您沒有看到任何活動資料，請嘗試變更日期範圍或 [篩選器](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="2af6c-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="2af6c-140">[一覽表] 頁面的其餘部分會在 [ **市場活動** ] 索引標籤上顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2af6c-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="2af6c-141">**名稱**</span><span class="sxs-lookup"><span data-stu-id="2af6c-141">**Name**</span></span>

- <span data-ttu-id="2af6c-142">**樣本主旨**：行銷活動中其中一個訊息的主旨列。</span><span class="sxs-lookup"><span data-stu-id="2af6c-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="2af6c-143">請注意，市場活動中的所有郵件不一定會有相同的主語。</span><span class="sxs-lookup"><span data-stu-id="2af6c-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="2af6c-144">**目標**：所計算的百分比： (組織中的活動收件者人數) / (服務) 中所有組織的收件者總數。</span><span class="sxs-lookup"><span data-stu-id="2af6c-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="2af6c-145">此值會指出只有組織中的市場活動所要使用的程度 (較高的值) 比對該服務中其他組織 () 較低的值。</span><span class="sxs-lookup"><span data-stu-id="2af6c-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="2af6c-146">**類型**：此值為 **網路釣魚** 或 **惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="2af6c-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="2af6c-147">**子類型**：此值包含有關活動的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2af6c-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="2af6c-148">例如：</span><span class="sxs-lookup"><span data-stu-id="2af6c-148">For example:</span></span>

  - <span data-ttu-id="2af6c-149">**網路釣魚**：在此 phished 中，您可以使用此市場活動的品牌。</span><span class="sxs-lookup"><span data-stu-id="2af6c-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="2af6c-150">例如，、、、 `Microsoft` `365` `Unknown` `Outlook` 或 `DocuSign` 。</span><span class="sxs-lookup"><span data-stu-id="2af6c-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="2af6c-151">**惡意**代碼：例如 `HTML/PHISH` 或 `HTML/<MalwareFamilyName>` 。</span><span class="sxs-lookup"><span data-stu-id="2af6c-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="2af6c-152">在此 phished 中，您可以使用此活動的品牌。</span><span class="sxs-lookup"><span data-stu-id="2af6c-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="2af6c-153">當以 ATP 技術為偵測時，會將前置詞 **ATP** 新增至子類型值。</span><span class="sxs-lookup"><span data-stu-id="2af6c-153">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="2af6c-154">**收件者**：此行銷活動鎖定的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="2af6c-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="2af6c-155">**Inboxed**：從其收件匣的此項活動接收郵件的使用者人數 (未傳遞到其 [垃圾郵件] 資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="2af6c-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="2af6c-156">按下：在網路釣魚郵件中 **，按一下 URL**或開啟附件的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="2af6c-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="2af6c-157">**按一下 [速率**：由「已**按一下**Inboxed」所計算的百分比  /  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="2af6c-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="2af6c-158">此值是活動之效能的指示器。</span><span class="sxs-lookup"><span data-stu-id="2af6c-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="2af6c-159">換句話說，如果收件者能夠將郵件識別為網路釣魚，而且沒有按一下 [負載 URL]。</span><span class="sxs-lookup"><span data-stu-id="2af6c-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="2af6c-160">請注意，惡意程式碼活動中不會使用 **點擊比率** 。</span><span class="sxs-lookup"><span data-stu-id="2af6c-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="2af6c-161">已**訪問**：有多少使用者實際將其設為 [負載] 網站。</span><span class="sxs-lookup"><span data-stu-id="2af6c-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="2af6c-162">如果有 **按一下** 的值，但安全連結已封鎖網站的存取權，這個值將會是零。</span><span class="sxs-lookup"><span data-stu-id="2af6c-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="2af6c-163">[ **市場活動來源** ] 索引標籤會顯示世界地圖上的郵件來源。</span><span class="sxs-lookup"><span data-stu-id="2af6c-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="2af6c-164">篩選和設定</span><span class="sxs-lookup"><span data-stu-id="2af6c-164">Filters and settings</span></span>

<span data-ttu-id="2af6c-165">在 [市場即時檢視] 頁面頂端，有數個篩選和查詢設定可協助您找出並隔離特定的市場活動。</span><span class="sxs-lookup"><span data-stu-id="2af6c-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![市場活動篩選](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="2af6c-167">您可以執行的最基本篩選為開始日期/時間和結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="2af6c-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="2af6c-168">若要進一步篩選視圖，您可以使用多個值篩選的單一屬性，方法是按一下 [**行銷活動類型**] 按鈕，進行選取，然後按一下 [重新整理 **]。**</span><span class="sxs-lookup"><span data-stu-id="2af6c-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="2af6c-169">下列清單說明可用的活動屬性：</span><span class="sxs-lookup"><span data-stu-id="2af6c-169">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="2af6c-170">Basic</span><span class="sxs-lookup"><span data-stu-id="2af6c-170">Basic</span></span>

  - <span data-ttu-id="2af6c-171">**行銷活動類型**：選取 **惡意** 代碼或 **網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="2af6c-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="2af6c-172">清除選取範圍與同時選取這兩者的結果相同。</span><span class="sxs-lookup"><span data-stu-id="2af6c-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="2af6c-173">**市場活動名稱**</span><span class="sxs-lookup"><span data-stu-id="2af6c-173">**Campaign name**</span></span>
  - <span data-ttu-id="2af6c-174">**活動子類型**</span><span class="sxs-lookup"><span data-stu-id="2af6c-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="2af6c-175">**Sender**</span><span class="sxs-lookup"><span data-stu-id="2af6c-175">**Sender**</span></span>
  - <span data-ttu-id="2af6c-176">**收件者**</span><span class="sxs-lookup"><span data-stu-id="2af6c-176">**Recipients**</span></span>
  - <span data-ttu-id="2af6c-177">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="2af6c-177">**Sender domain**</span></span>
  - <span data-ttu-id="2af6c-178">**Subject**</span><span class="sxs-lookup"><span data-stu-id="2af6c-178">**Subject**</span></span>
  - <span data-ttu-id="2af6c-179">**附件檔名**</span><span class="sxs-lookup"><span data-stu-id="2af6c-179">**Attachment filename**</span></span>
  - <span data-ttu-id="2af6c-180">**惡意程式碼系列**</span><span class="sxs-lookup"><span data-stu-id="2af6c-180">**Malware family**</span></span>
  - <span data-ttu-id="2af6c-181">**傳遞動作**</span><span class="sxs-lookup"><span data-stu-id="2af6c-181">**Delivery action**</span></span>
  - <span data-ttu-id="2af6c-182">**偵測技術**</span><span class="sxs-lookup"><span data-stu-id="2af6c-182">**Detection technology**</span></span>
  - <span data-ttu-id="2af6c-183">**標記**</span><span class="sxs-lookup"><span data-stu-id="2af6c-183">**Tags**</span></span>
  - <span data-ttu-id="2af6c-184">**系統覆寫**</span><span class="sxs-lookup"><span data-stu-id="2af6c-184">**System overrides**</span></span>

- <span data-ttu-id="2af6c-185">進階</span><span class="sxs-lookup"><span data-stu-id="2af6c-185">Advanced</span></span>

  - <span data-ttu-id="2af6c-186">**網際網路郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中提供。</span><span class="sxs-lookup"><span data-stu-id="2af6c-186">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="2af6c-187">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="2af6c-187">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="2af6c-188">**網路消息識別碼**：在郵件頭的 [ **X-MS-Exchange-Organization-網路 Message-Id** 標頭] 欄位中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="2af6c-188">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="2af6c-189">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="2af6c-189">**Sender IP**</span></span>
  
  - <span data-ttu-id="2af6c-190">**附件 SHA256**：若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令： `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="2af6c-190">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="2af6c-191">**叢集識別碼**</span><span class="sxs-lookup"><span data-stu-id="2af6c-191">**Cluster ID**</span></span>
  
  - <span data-ttu-id="2af6c-192">**警示原則識別碼**</span><span class="sxs-lookup"><span data-stu-id="2af6c-192">**Alert Policy ID**</span></span>

- <span data-ttu-id="2af6c-193">URL</span><span class="sxs-lookup"><span data-stu-id="2af6c-193">URLs</span></span>

  - <span data-ttu-id="2af6c-194">**URL 網域**</span><span class="sxs-lookup"><span data-stu-id="2af6c-194">**URL domain**</span></span>
  - <span data-ttu-id="2af6c-195">**URL 網域和路徑**</span><span class="sxs-lookup"><span data-stu-id="2af6c-195">**URL domain and path**</span></span>
  - <span data-ttu-id="2af6c-196">**URL**</span><span class="sxs-lookup"><span data-stu-id="2af6c-196">**URL**</span></span>
  - <span data-ttu-id="2af6c-197">**URL 路徑**</span><span class="sxs-lookup"><span data-stu-id="2af6c-197">**URL path**</span></span>
  - <span data-ttu-id="2af6c-198">**按一下 [判定]**</span><span class="sxs-lookup"><span data-stu-id="2af6c-198">**Click verdict**</span></span>

<span data-ttu-id="2af6c-199">如需更多的高級篩選，包括多個屬性篩選，您可以按一下 [ **高級篩選** ] 按鈕建立查詢。</span><span class="sxs-lookup"><span data-stu-id="2af6c-199">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="2af6c-200">您可以使用相同的活動屬性，但有下列增強功能：</span><span class="sxs-lookup"><span data-stu-id="2af6c-200">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="2af6c-201">您可以按一下 [ **新增條件** ]，以選取多個條件。</span><span class="sxs-lookup"><span data-stu-id="2af6c-201">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="2af6c-202">您可以選擇條件之間的 **And** 或 **or** 運算子。</span><span class="sxs-lookup"><span data-stu-id="2af6c-202">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="2af6c-203">您可以選取 [條件] 清單底部的 [ **條件] 群組** 專案，以形成複雜的複合條件。</span><span class="sxs-lookup"><span data-stu-id="2af6c-203">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="2af6c-204">完成作業後，請按一下 [ **查詢** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="2af6c-204">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="2af6c-205">在您建立基本或高級篩選器之後，您可以使用 [ **儲存查詢** ] 或 [ **另存查詢**] 來儲存。</span><span class="sxs-lookup"><span data-stu-id="2af6c-205">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="2af6c-206">之後，當您回到 [市場活動] 視圖時，您可以按一下 [ **已儲存的查詢設定**] 載入已儲存的篩選。</span><span class="sxs-lookup"><span data-stu-id="2af6c-206">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="2af6c-207">若要匯出圖形或行銷清單，請按一下 [ **匯出** ]，然後選取 [ **匯出圖表資料** ] 或 [ **匯出活動清單**]。</span><span class="sxs-lookup"><span data-stu-id="2af6c-207">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="2af6c-208">如果您有 Microsoft Defender ATP 訂閱，您可以按一下 [ **WDATP** ]，使用 MICROSOFT defender atp 連線或中斷市場活動資訊的連線。</span><span class="sxs-lookup"><span data-stu-id="2af6c-208">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="2af6c-209">如需詳細資訊，請參閱將 [Office 365 atp 與 Microsoft DEFENDER Atp 整合](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="2af6c-209">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="2af6c-210">行銷活動詳細資料</span><span class="sxs-lookup"><span data-stu-id="2af6c-210">Campaign details</span></span>

<span data-ttu-id="2af6c-211">當您按一下市場活動的名稱時，市場活動詳細資料會出現在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="2af6c-211">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="2af6c-212">活動資訊</span><span class="sxs-lookup"><span data-stu-id="2af6c-212">Campaign information</span></span>

<span data-ttu-id="2af6c-213">在 [市場活動詳細資料] 視圖的頂端，可取得下列活動資訊：</span><span class="sxs-lookup"><span data-stu-id="2af6c-213">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="2af6c-214">**識別碼**：唯一的活動識別碼。</span><span class="sxs-lookup"><span data-stu-id="2af6c-214">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="2af6c-215">**開始** 和 **結束**：活動的開始日期和結束日期。</span><span class="sxs-lookup"><span data-stu-id="2af6c-215">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="2af6c-216">請注意，這些日期可能會比您在 [概覽] 頁面上選取的篩選日期進一步擴充。</span><span class="sxs-lookup"><span data-stu-id="2af6c-216">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="2af6c-217">**影響**：此區段包含您在 [時程表]) 中所選取之日期範圍篩選的下列資料 (：</span><span class="sxs-lookup"><span data-stu-id="2af6c-217">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="2af6c-218">收件者總數。</span><span class="sxs-lookup"><span data-stu-id="2af6c-218">The total number of recipients.</span></span>
  - <span data-ttu-id="2af6c-219">傳送至收件匣但不是 [垃圾郵件 (] 資料夾) 的「Inboxed」郵件數目。</span><span class="sxs-lookup"><span data-stu-id="2af6c-219">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="2af6c-220">在網路釣魚郵件中按一下 URL 負載的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="2af6c-220">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="2af6c-221">Howe 許多使用者已訪問 URL。</span><span class="sxs-lookup"><span data-stu-id="2af6c-221">Howe many users visited the URL.</span></span>

- <span data-ttu-id="2af6c-222">**目標**：所計算的百分比： (組織中的活動收件者人數) / (服務) 中所有組織的收件者總數。</span><span class="sxs-lookup"><span data-stu-id="2af6c-222">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="2af6c-223">請注意，此值是透過整個活動週期計算的，而不會根據日期篩選器而變更。</span><span class="sxs-lookup"><span data-stu-id="2af6c-223">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="2af6c-224">市場活動活動的互動時程表：時程表會顯示活動的整個生命週期中的活動。</span><span class="sxs-lookup"><span data-stu-id="2af6c-224">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="2af6c-225">根據預設，陰影區域會包含您在 [概覽] 中選取的日期範圍篩選。</span><span class="sxs-lookup"><span data-stu-id="2af6c-225">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="2af6c-226">您可以按一下並拖動以選取特定的起點和終點， <u>它會變更顯示在 [ **影響** ] 區域中的資料，以及下一節所述的頁面的其餘</u>部分。</span><span class="sxs-lookup"><span data-stu-id="2af6c-226">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="2af6c-227">在標題列中，您可以按一下 [ **下載活動] 調** 高按鈕 ![ 下載活動上寫圖示 ](../../media/download-campaign-write-up-button.png) ，以將市場活動詳細資料下載至 Word 檔 (預設會以名稱 CampaignReport.docx) 為單位。</span><span class="sxs-lookup"><span data-stu-id="2af6c-227">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="2af6c-228">請注意，下載包含整個市場活動的整個生命週期的詳細資料，而不只是 (您) 所選取的篩選日期。</span><span class="sxs-lookup"><span data-stu-id="2af6c-228">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![活動資訊](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="2af6c-230">行銷活動流程</span><span class="sxs-lookup"><span data-stu-id="2af6c-230">Campaign flow</span></span>

<span data-ttu-id="2af6c-231">在 [市場活動詳細資料] 視圖中，市場活動的重要詳細資料會顯示在水準流程圖中的 [ **流程** ] 區段中 (稱為 _Sankey_ 圖表) 。</span><span class="sxs-lookup"><span data-stu-id="2af6c-231">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="2af6c-232">這些詳細資料將協助您了解行銷活動的元素和在組織中的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="2af6c-232">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="2af6c-233">**流程圖**中所顯示的資訊是由時程表中的陰影日期範圍所控制，如上一節所述。</span><span class="sxs-lookup"><span data-stu-id="2af6c-233">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![未包含使用者 URL 點選的行銷活動詳細資料](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="2af6c-235">如果您將游標停留在圖表中的水平帶狀上，您會看到相關訊息的數量 (例如來自特定來源 IP 的訊息、來自使用特定寄件者網域來源 IP 的訊息等)。</span><span class="sxs-lookup"><span data-stu-id="2af6c-235">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="2af6c-236">圖表中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2af6c-236">The diagram contains the following information:</span></span>

- <span data-ttu-id="2af6c-237">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="2af6c-237">**Sender IPs**</span></span>

- <span data-ttu-id="2af6c-238">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="2af6c-238">**Sender domains**</span></span>

- <span data-ttu-id="2af6c-239">**篩選 verdicts**：值與 [反垃圾郵件郵件頭](anti-spam-message-headers.md)中所述的可用網路釣魚和垃圾郵件篩選 verdicts 有關。</span><span class="sxs-lookup"><span data-stu-id="2af6c-239">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="2af6c-240">下表說明可用的值：</span><span class="sxs-lookup"><span data-stu-id="2af6c-240">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="2af6c-241">值</span><span class="sxs-lookup"><span data-stu-id="2af6c-241">Value</span></span>|<span data-ttu-id="2af6c-242">垃圾郵件篩選判定</span><span class="sxs-lookup"><span data-stu-id="2af6c-242">Spam filter verdict</span></span>|<span data-ttu-id="2af6c-243">描述</span><span class="sxs-lookup"><span data-stu-id="2af6c-243">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="2af6c-244">**允許**</span><span class="sxs-lookup"><span data-stu-id="2af6c-244">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="2af6c-245">垃圾郵件篩選評估之前，郵件已標示為非垃圾郵件和/或略過的篩選。</span><span class="sxs-lookup"><span data-stu-id="2af6c-245">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="2af6c-246">例如，郵件流程規則（也稱為傳輸規則) ）將郵件標示為非垃圾郵件 (。</span><span class="sxs-lookup"><span data-stu-id="2af6c-246">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span><br/><br/><span data-ttu-id="2af6c-247">郵件因其他原因而略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="2af6c-247">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="2af6c-248">例如，寄件者和收件者似乎位於相同組織中。</span><span class="sxs-lookup"><span data-stu-id="2af6c-248">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="2af6c-249">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="2af6c-249">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="2af6c-250">垃圾郵件篩選評估之前，郵件已標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="2af6c-250">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="2af6c-251">例如，依郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="2af6c-251">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="2af6c-252">**已偵測**</span><span class="sxs-lookup"><span data-stu-id="2af6c-252">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="2af6c-253">垃圾郵件篩選已將此郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="2af6c-253">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="2af6c-254">**未偵測到**</span><span class="sxs-lookup"><span data-stu-id="2af6c-254">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="2af6c-255">郵件已由垃圾郵件篩選標示為非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="2af6c-255">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="2af6c-256">**釋放**</span><span class="sxs-lookup"><span data-stu-id="2af6c-256">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="2af6c-257">郵件因從隔離區發行而略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="2af6c-257">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="2af6c-258">**承租人允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2af6c-258">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="2af6c-259">由於反垃圾郵件原則中的設定，郵件會略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="2af6c-259">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="2af6c-260">例如，寄件者位於允許的寄件者清單或允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="2af6c-260">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="2af6c-261">**租使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="2af6c-261">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="2af6c-262">由於反垃圾郵件原則中的設定，郵件已被垃圾郵件篩選封鎖。</span><span class="sxs-lookup"><span data-stu-id="2af6c-262">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="2af6c-263">例如，寄件者位於允許的寄件者清單或允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="2af6c-263">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="2af6c-264">**使用者允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2af6c-264">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="2af6c-265">因為寄件者位於使用者的安全寄件者清單中，郵件會略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="2af6c-265">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="2af6c-266">**使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="2af6c-266">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="2af6c-267">郵件被垃圾郵件篩選封鎖，因為寄件者是在使用者的封鎖寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="2af6c-267">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="2af6c-268">**幹掉**</span><span class="sxs-lookup"><span data-stu-id="2af6c-268">**ZAP**</span></span>|<span data-ttu-id="2af6c-269">不適用</span><span class="sxs-lookup"><span data-stu-id="2af6c-269">n/a</span></span>|<span data-ttu-id="2af6c-270">[零小時自動清除 (ZAP) ](zero-hour-auto-purge.md) 將傳遞的郵件移至 [垃圾郵件] 資料夾或隔離區。</span><span class="sxs-lookup"><span data-stu-id="2af6c-270">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="2af6c-271">您可以設定反垃圾郵件原則中的動作。</span><span class="sxs-lookup"><span data-stu-id="2af6c-271">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="2af6c-272"><sup>\*</sup> 請複查您的反垃圾郵件原則，因為服務可能封鎖允許的郵件。</span><span class="sxs-lookup"><span data-stu-id="2af6c-272"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="2af6c-273"><sup>\*\*</sup> 請複查您的反垃圾郵件原則，因為應該隔離這些郵件，而非傳遞。</span><span class="sxs-lookup"><span data-stu-id="2af6c-273"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="2af6c-274">**傳遞位置**：您可能想要調查傳送給收件者的郵件 (至收件匣或 [垃圾郵件] 資料夾) ，即使使用者未按一下郵件中的 [載荷] URL 也是一樣。</span><span class="sxs-lookup"><span data-stu-id="2af6c-274">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="2af6c-275">您也可以從隔離區中移除隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="2af6c-275">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="2af6c-276">如需詳細資訊，請參閱 [在 EOP 中隔離的電子郵件訊息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2af6c-276">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="2af6c-277">**已刪除資料夾**</span><span class="sxs-lookup"><span data-stu-id="2af6c-277">**Deleted folder**</span></span>
  - <span data-ttu-id="2af6c-278">**下降**</span><span class="sxs-lookup"><span data-stu-id="2af6c-278">**Dropped**</span></span>
  - <span data-ttu-id="2af6c-279">**外部**：收件者位於您的內部部署電子郵件組織中的混合式環境。</span><span class="sxs-lookup"><span data-stu-id="2af6c-279">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="2af6c-280">**已失敗**</span><span class="sxs-lookup"><span data-stu-id="2af6c-280">**Failed**</span></span>
  - <span data-ttu-id="2af6c-281">**轉發**</span><span class="sxs-lookup"><span data-stu-id="2af6c-281">**Forwarded**</span></span>
  - <span data-ttu-id="2af6c-282">**收件匣**</span><span class="sxs-lookup"><span data-stu-id="2af6c-282">**Inbox**</span></span>
  - <span data-ttu-id="2af6c-283">**垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="2af6c-283">**Junk folder**</span></span>
  - <span data-ttu-id="2af6c-284">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="2af6c-284">**Quarantine**</span></span>
  - <span data-ttu-id="2af6c-285">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="2af6c-285">**Unknown**</span></span>

- <span data-ttu-id="2af6c-286">**URL 按一下**：這些值會在下一節中說明。</span><span class="sxs-lookup"><span data-stu-id="2af6c-286">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="2af6c-287">在所有包含超過10個專案的層中，會顯示前10個專案，而其餘專案則會結合在 **其他**專案中。</span><span class="sxs-lookup"><span data-stu-id="2af6c-287">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="2af6c-288">URL 點選</span><span class="sxs-lookup"><span data-stu-id="2af6c-288">URL clicks</span></span>

<span data-ttu-id="2af6c-289">當仿冒郵件傳送至收件者的收件匣或 [垃圾郵件] 資料夾時，使用者永遠都有可能會按一下 [負載 URL]。</span><span class="sxs-lookup"><span data-stu-id="2af6c-289">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="2af6c-290">不是按一下 URL 是一項很小的成功，但是您必須決定網路釣魚郵件甚至傳遞到信箱的原因。</span><span class="sxs-lookup"><span data-stu-id="2af6c-290">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="2af6c-291">如果使用者按一下網路釣魚郵件中的 [負載 URL]，則動作會顯示在 [市場活動詳細資料] 視圖中圖表的 [ **URL 按一下** ] 區域中。</span><span class="sxs-lookup"><span data-stu-id="2af6c-291">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="2af6c-292">**允許**</span><span class="sxs-lookup"><span data-stu-id="2af6c-292">**Allowed**</span></span>

- <span data-ttu-id="2af6c-293">**BlockPage**：收件者已按一下有效載荷 URL，但組織中的 [安全連結](atp-safe-links.md) 原則已封鎖其對惡意網站的存取。</span><span class="sxs-lookup"><span data-stu-id="2af6c-293">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>

- <span data-ttu-id="2af6c-294">**BlockPageOverride**：收件者按一下了郵件中的 [負載 URL]，則安全連結會嘗試將其停止，但允許覆寫區塊。</span><span class="sxs-lookup"><span data-stu-id="2af6c-294">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="2af6c-295">檢查您的 [安全連結原則](set-up-atp-safe-links-policies.md) ，以瞭解使用者為何可以覆寫安全連結判定，並繼續進行惡意網站。</span><span class="sxs-lookup"><span data-stu-id="2af6c-295">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="2af6c-296">**PendingDetonationPage**： OFFICE 365 ATP 中的安全附件是在虛擬電腦環境中開啟及調查負載 URL 的過程中。</span><span class="sxs-lookup"><span data-stu-id="2af6c-296">**PendingDetonationPage**: Safe Attachments in Office 365 ATP is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>

- <span data-ttu-id="2af6c-297">**PendingDetonationPageOverride**：收件者可以覆寫 [負載引爆] 處理常式，並開啟 URL，而不會等候結果。</span><span class="sxs-lookup"><span data-stu-id="2af6c-297">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="2af6c-298">索引標籤</span><span class="sxs-lookup"><span data-stu-id="2af6c-298">Tabs</span></span>

<span data-ttu-id="2af6c-299">[市場活動詳細資料] 視圖中的索引標籤可讓您進一步調查市場活動。</span><span class="sxs-lookup"><span data-stu-id="2af6c-299">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="2af6c-300">在 [ [活動資訊](#campaign-information) ] 區段中所述的時程表中，依陰影日期範圍所控制的索引標籤上顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="2af6c-300">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="2af6c-301">**URL 按一下**：如果使用者沒有按一下郵件中的 [負載 URL]，此區段將會是空白的。</span><span class="sxs-lookup"><span data-stu-id="2af6c-301">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="2af6c-302">如果使用者能夠按一下 URL，則會填入下列值：</span><span class="sxs-lookup"><span data-stu-id="2af6c-302">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="2af6c-303">**使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2af6c-303">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="2af6c-304">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2af6c-304">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="2af6c-305">**按一下 [時間]**</span><span class="sxs-lookup"><span data-stu-id="2af6c-305">**Click time**</span></span>
  - <span data-ttu-id="2af6c-306">**按一下 [判定]**</span><span class="sxs-lookup"><span data-stu-id="2af6c-306">**Click verdict**</span></span>

- <span data-ttu-id="2af6c-307">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="2af6c-307">**Sender IPs**</span></span>

  - <span data-ttu-id="2af6c-308">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2af6c-308">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="2af6c-309">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="2af6c-309">**Total count**</span></span>
  - <span data-ttu-id="2af6c-310">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="2af6c-310">**Inboxed**</span></span>
  - <span data-ttu-id="2af6c-311">**非 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="2af6c-311">**Not Inboxed**</span></span>
  - <span data-ttu-id="2af6c-312">已**通過的 SPF**：寄件者[原則框架 (SPF) ](how-office-365-uses-spf-to-prevent-spoofing.md)驗證寄件者。</span><span class="sxs-lookup"><span data-stu-id="2af6c-312">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="2af6c-313">未通過 SPF 驗證的寄件者表示未驗證寄件者，或郵件是哄騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="2af6c-313">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="2af6c-314">**寄件者**</span><span class="sxs-lookup"><span data-stu-id="2af6c-314">**Senders**</span></span>

  - <span data-ttu-id="2af6c-315">**寄件者**：這是 SMTP MAIL FROM 命令中的實際寄件者位址，不一定是使用者在其電子郵件客戶程式中看到的寄件者：電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2af6c-315">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="2af6c-316">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="2af6c-316">**Total count**</span></span>
  - <span data-ttu-id="2af6c-317">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="2af6c-317">**Inboxed**</span></span>
  - <span data-ttu-id="2af6c-318">**非 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="2af6c-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="2af6c-319">**DKIM 通過**：寄件者是由 [識別為郵件 (DKIM) 的網域金鑰 ](support-for-validation-of-dkim-signed-messages.md)所驗證。</span><span class="sxs-lookup"><span data-stu-id="2af6c-319">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="2af6c-320">未通過 DKIM 驗證的寄件者表示未驗證寄件者，或郵件為偽造合法寄件者。</span><span class="sxs-lookup"><span data-stu-id="2af6c-320">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="2af6c-321">已**通過 DMARC**：寄件者是透過以[網域為基礎的郵件驗證、報告和一致性 (DMARC) ](use-dmarc-to-validate-email.md)進行驗證。</span><span class="sxs-lookup"><span data-stu-id="2af6c-321">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="2af6c-322">未通過 DMARC 驗證的寄件者表示未驗證寄件者，或郵件為偽造合法寄件者。</span><span class="sxs-lookup"><span data-stu-id="2af6c-322">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="2af6c-323">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="2af6c-323">**Attachments**</span></span>

  - <span data-ttu-id="2af6c-324">**Filename**</span><span class="sxs-lookup"><span data-stu-id="2af6c-324">**Filename**</span></span>
  - <span data-ttu-id="2af6c-325">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="2af6c-325">**SHA256**</span></span>
  - <span data-ttu-id="2af6c-326">**惡意程式碼系列**</span><span class="sxs-lookup"><span data-stu-id="2af6c-326">**Malware family**</span></span>
  - <span data-ttu-id="2af6c-327">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="2af6c-327">**Total count**</span></span>

- <span data-ttu-id="2af6c-328">**URL**</span><span class="sxs-lookup"><span data-stu-id="2af6c-328">**URL**</span></span>

  - <span data-ttu-id="2af6c-329">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2af6c-329">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="2af6c-330">**總數**</span><span class="sxs-lookup"><span data-stu-id="2af6c-330">**Total Count**</span></span>

<span data-ttu-id="2af6c-331"><sup>\*</sup> 按一下此值會開啟新的飛出畫面，其中在行銷活動詳細資料檢視上方包含更多有關指定項目 (使用者、URL 等) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2af6c-331"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="2af6c-332">若要回到行銷活動詳細資料檢視，請按一下新飛出視窗中的 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2af6c-332">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="2af6c-333">按鈕</span><span class="sxs-lookup"><span data-stu-id="2af6c-333">Buttons</span></span>

<span data-ttu-id="2af6c-334">行銷活動詳細資料檢視中的按鈕可讓您使用威脅瀏覽器的強大功能，進一步調查行銷活動。</span><span class="sxs-lookup"><span data-stu-id="2af6c-334">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="2af6c-335">**探索行銷活動**：使用 [行銷活動識別碼]\*\*\*\* 值做為搜尋篩選，以開啟新的威脅總管搜尋索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2af6c-335">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="2af6c-336">**探索 Inboxed 郵件**：開啟新的威脅瀏覽器搜尋索引標籤，使用 **活動識別碼** 及 **傳遞位置：收件** 匣做為搜尋篩選器。</span><span class="sxs-lookup"><span data-stu-id="2af6c-336">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
