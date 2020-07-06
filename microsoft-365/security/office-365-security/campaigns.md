---
title: ATP 中的即時檢視
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
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039450"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="b2952-103">ATP 中的即時檢視</span><span class="sxs-lookup"><span data-stu-id="b2952-103">Campaign Views in ATP</span></span>

<span data-ttu-id="b2952-104">[活動] 視圖是「安全性 & 規範中心」中的高級威脅防護（ATP）中的一項功能，可用於識別和分類服務中的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="b2952-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="b2952-105">行銷活動檢視可協助您：</span><span class="sxs-lookup"><span data-stu-id="b2952-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="b2952-106">更有效率地調查和回應網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="b2952-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="b2952-107">更進一步了解攻擊範圍。</span><span class="sxs-lookup"><span data-stu-id="b2952-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="b2952-108">向決策者展現價值。</span><span class="sxs-lookup"><span data-stu-id="b2952-108">Show value to decision makers.</span></span>

<span data-ttu-id="b2952-109">行銷活動檢視可讓您較任何人類所能夠，更快速且更完整地查看攻擊的全貌。</span><span class="sxs-lookup"><span data-stu-id="b2952-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="b2952-110">什麼是行銷活動？</span><span class="sxs-lookup"><span data-stu-id="b2952-110">What is a campaign?</span></span>

<span data-ttu-id="b2952-111">行銷活動是針對一或多個組織的協調式電子郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="b2952-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="b2952-112">竊取認證及公司資料的電子郵件攻擊是一種大型且 lucrative 的行業。</span><span class="sxs-lookup"><span data-stu-id="b2952-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="b2952-113">隨著技術不斷增加以停止攻擊的努力，攻擊者會修改其方法，以確保持續成功。</span><span class="sxs-lookup"><span data-stu-id="b2952-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="b2952-114">Microsoft 會利用整個服務中大量的反網路釣魚、反垃圾郵件和反惡意程式碼資料，協助識別市場活動。</span><span class="sxs-lookup"><span data-stu-id="b2952-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="b2952-115">我們會根據數個因素來分析和分類攻擊資訊。</span><span class="sxs-lookup"><span data-stu-id="b2952-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="b2952-116">例如：</span><span class="sxs-lookup"><span data-stu-id="b2952-116">For example:</span></span>

- <span data-ttu-id="b2952-117">**攻擊來源**：來源 IP 位址和寄件者電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="b2952-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="b2952-118">**攻擊郵件**內容：郵件的內容、樣式和音調。</span><span class="sxs-lookup"><span data-stu-id="b2952-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="b2952-119">**攻擊收件者**：收件者網域、收件者工作職掌 (系統管理員、執行人員等)、公司類型 (大型、小型、公有、私人等等) 以及產業。</span><span class="sxs-lookup"><span data-stu-id="b2952-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="b2952-120">**攻擊負載**：郵件中的惡意連結、附件或其他負載。</span><span class="sxs-lookup"><span data-stu-id="b2952-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="b2952-121">市場活動可能會短期，或可能跨越數天、數周或數天，具有有效和非使用中的期間。</span><span class="sxs-lookup"><span data-stu-id="b2952-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="b2952-122">您的特定組織可能會發起一個市場活動，否則您的組織可能會是多個公司的較大活動的一部分。</span><span class="sxs-lookup"><span data-stu-id="b2952-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="b2952-123">即時檢視安全性 & 規範中心</span><span class="sxs-lookup"><span data-stu-id="b2952-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="b2952-124">在**威脅管理**活動的[安全性 & 規範中心](https://protection.office.com) \> \*\* \*\*，或是直接在中提供即時檢視 <https://protection.office.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="b2952-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![安全性與合規性中心的行銷活動概觀](../../media/campaigns-overview.png)

<span data-ttu-id="b2952-126">您也可以從下列來源取得市場即時檢視：</span><span class="sxs-lookup"><span data-stu-id="b2952-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="b2952-127">**威脅管理** \>**瀏覽器** \>**View** \>**活動**</span><span class="sxs-lookup"><span data-stu-id="b2952-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="b2952-128">**威脅管理** \>**瀏覽器** \>**View** \>**所有電子郵件** \>[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b2952-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="b2952-129">**威脅管理** \>**瀏覽器** \>**View** \>**網路釣魚** \>[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b2952-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="b2952-130">**威脅管理** \>**瀏覽器** \>**View** \>**惡意** \> 代碼[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b2952-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="b2952-131">若要存取市場即時檢視，您必須是 Security & 合規性中心內的**組織管理**、**安全性管理員**或**安全性讀者**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b2952-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="b2952-132">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b2952-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="b2952-133">市場活動概覽</span><span class="sxs-lookup"><span data-stu-id="b2952-133">Campaigns overview</span></span>

<span data-ttu-id="b2952-134">[一覽表] 頁面會顯示所有市場活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b2952-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="b2952-135">在 [預設**市場活動**] 索引標籤上，[**行銷活動類型**] 區域會顯示柱狀圖圖，顯示每日的收件者人數。</span><span class="sxs-lookup"><span data-stu-id="b2952-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="b2952-136">根據預設，圖表會顯示**網路釣魚**和**惡意**代碼資料。</span><span class="sxs-lookup"><span data-stu-id="b2952-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="b2952-137">如果您沒有看到任何活動資料，請嘗試變更日期範圍或[篩選器](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="b2952-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="b2952-138">[一覽表] 頁面的其餘部分會在 [**市場活動**] 索引標籤上顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b2952-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="b2952-139">**名稱**</span><span class="sxs-lookup"><span data-stu-id="b2952-139">**Name**</span></span>

- <span data-ttu-id="b2952-140">**樣本主旨**：行銷活動中其中一個訊息的主旨列。</span><span class="sxs-lookup"><span data-stu-id="b2952-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="b2952-141">請注意，市場活動中的所有郵件不一定會有相同的主語。</span><span class="sxs-lookup"><span data-stu-id="b2952-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="b2952-142">**目標**：所計算的百分比：（組織中的活動收件者數目）/（該服務中所有組織的收件者總數）。</span><span class="sxs-lookup"><span data-stu-id="b2952-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="b2952-143">此值表示市場活動特別導向組織的程度（較高的值）與導向其他組織在服務中的位置（低值）。</span><span class="sxs-lookup"><span data-stu-id="b2952-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="b2952-144">**類型**：此值為**網路釣魚**或**惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="b2952-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="b2952-145">**子類型**：此值包含有關活動的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b2952-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="b2952-146">例如：</span><span class="sxs-lookup"><span data-stu-id="b2952-146">For example:</span></span>

  - <span data-ttu-id="b2952-147">**網路釣魚**：在此 phished 中，您可以使用此市場活動的品牌。</span><span class="sxs-lookup"><span data-stu-id="b2952-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="b2952-148">例如，、、、 `Microsoft` `365` `Unknown` `Outlook` 或 `DocuSign` 。</span><span class="sxs-lookup"><span data-stu-id="b2952-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="b2952-149">**惡意**代碼：例如 `HTML/PHISH` 或 `HTML/<MalwareFamilyName>` 。</span><span class="sxs-lookup"><span data-stu-id="b2952-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="b2952-150">在此 phished 中，您可以使用此活動的品牌。</span><span class="sxs-lookup"><span data-stu-id="b2952-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="b2952-151">當以 ATP 技術為偵測時，會將前置詞**ATP**新增至子類型值。</span><span class="sxs-lookup"><span data-stu-id="b2952-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="b2952-152">**收件者**：此行銷活動鎖定的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="b2952-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="b2952-153">**Inboxed**：從其收件匣的此活動接收郵件的使用者人數（未傳遞到其 [垃圾郵件] 資料夾）。</span><span class="sxs-lookup"><span data-stu-id="b2952-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="b2952-154">按下：在網路釣魚郵件中 **，按一下 URL**或開啟附件的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="b2952-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="b2952-155">**按一下 [速率**：由「已**按一下**Inboxed」所計算的百分比  /  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="b2952-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="b2952-156">此值是活動之效能的指示器，以及收件者是否可以將郵件識別為網路釣魚，並避免按一下 [負載 URL]。</span><span class="sxs-lookup"><span data-stu-id="b2952-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="b2952-157">請注意，惡意軟體活動中不會使用此值。</span><span class="sxs-lookup"><span data-stu-id="b2952-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="b2952-158">已**訪問**：有多少使用者實際將其設為 [負載] 網站。</span><span class="sxs-lookup"><span data-stu-id="b2952-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="b2952-159">如果有**按一下**的值，但安全連結已封鎖網站的存取權，這個值將會是零。</span><span class="sxs-lookup"><span data-stu-id="b2952-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="b2952-160">[**市場活動來源**] 索引標籤會顯示世界地圖上的郵件來源。</span><span class="sxs-lookup"><span data-stu-id="b2952-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="b2952-161">篩選和設定</span><span class="sxs-lookup"><span data-stu-id="b2952-161">Filters and settings</span></span>

<span data-ttu-id="b2952-162">在 [市場即時檢視] 頁面頂端，有數個篩選和查詢設定可協助您找出並隔離特定的市場活動。</span><span class="sxs-lookup"><span data-stu-id="b2952-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![市場活動篩選](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="b2952-164">您可以執行的最基本篩選為開始日期/時間和結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="b2952-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="b2952-165">若要進一步篩選視圖，您可以使用多個值篩選的單一屬性，方法是按一下 [**行銷活動類型**] 按鈕，進行選取，然後按一下 [重新整理 **]。**</span><span class="sxs-lookup"><span data-stu-id="b2952-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="b2952-166">下列清單說明可用的活動屬性：</span><span class="sxs-lookup"><span data-stu-id="b2952-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="b2952-167">基本</span><span class="sxs-lookup"><span data-stu-id="b2952-167">Basic</span></span>

  - <span data-ttu-id="b2952-168">**行銷活動類型**：選取**惡意**代碼或**網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="b2952-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="b2952-169">清除選取範圍與同時選取這兩者的結果相同。</span><span class="sxs-lookup"><span data-stu-id="b2952-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="b2952-170">**市場活動名稱**</span><span class="sxs-lookup"><span data-stu-id="b2952-170">**Campaign name**</span></span>
  - <span data-ttu-id="b2952-171">**活動子類型**</span><span class="sxs-lookup"><span data-stu-id="b2952-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="b2952-172">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b2952-172">**Sender**</span></span>
  - <span data-ttu-id="b2952-173">**收件者**</span><span class="sxs-lookup"><span data-stu-id="b2952-173">**Recipients**</span></span>
  - <span data-ttu-id="b2952-174">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="b2952-174">**Sender domain**</span></span>
  - <span data-ttu-id="b2952-175">**主旨**</span><span class="sxs-lookup"><span data-stu-id="b2952-175">**Subject**</span></span>
  - <span data-ttu-id="b2952-176">**附件檔名**</span><span class="sxs-lookup"><span data-stu-id="b2952-176">**Attachment filename**</span></span>
  - <span data-ttu-id="b2952-177">**惡意程式碼系列**</span><span class="sxs-lookup"><span data-stu-id="b2952-177">**Malware family**</span></span>
  - <span data-ttu-id="b2952-178">**傳遞動作**</span><span class="sxs-lookup"><span data-stu-id="b2952-178">**Delivery action**</span></span>
  - <span data-ttu-id="b2952-179">**偵測技術**</span><span class="sxs-lookup"><span data-stu-id="b2952-179">**Detection technology**</span></span>
  - <span data-ttu-id="b2952-180">**標記**</span><span class="sxs-lookup"><span data-stu-id="b2952-180">**Tags**</span></span>
  - <span data-ttu-id="b2952-181">**系統覆寫**</span><span class="sxs-lookup"><span data-stu-id="b2952-181">**System overrides**</span></span>

- <span data-ttu-id="b2952-182">進階</span><span class="sxs-lookup"><span data-stu-id="b2952-182">Advanced</span></span>

  - <span data-ttu-id="b2952-183">**網際網路郵件識別碼**：郵件頭的**Message-ID**標頭欄位中提供。</span><span class="sxs-lookup"><span data-stu-id="b2952-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="b2952-184">範例值為 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` （記下角括弧）。</span><span class="sxs-lookup"><span data-stu-id="b2952-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="b2952-185">**網路消息識別碼**：在郵件頭的 [ **X-MS-Exchange-Organization-網路 Message-Id**標頭] 欄位中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="b2952-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="b2952-186">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="b2952-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="b2952-187">**附件 SHA256**：若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令： `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="b2952-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="b2952-188">**叢集識別碼**</span><span class="sxs-lookup"><span data-stu-id="b2952-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="b2952-189">**警示原則識別碼**</span><span class="sxs-lookup"><span data-stu-id="b2952-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="b2952-190">URL</span><span class="sxs-lookup"><span data-stu-id="b2952-190">URLs</span></span>

  - <span data-ttu-id="b2952-191">**URL 網域**</span><span class="sxs-lookup"><span data-stu-id="b2952-191">**URL domain**</span></span>
  - <span data-ttu-id="b2952-192">**URL 網域和路徑**</span><span class="sxs-lookup"><span data-stu-id="b2952-192">**URL domain and path**</span></span>
  - <span data-ttu-id="b2952-193">[URL]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b2952-193">**URL**</span></span>
  - <span data-ttu-id="b2952-194">**URL 路徑**</span><span class="sxs-lookup"><span data-stu-id="b2952-194">**URL path**</span></span>
  - <span data-ttu-id="b2952-195">**按一下 [判定]**</span><span class="sxs-lookup"><span data-stu-id="b2952-195">**Click verdict**</span></span>

<span data-ttu-id="b2952-196">如需更多的高級篩選，包括多個屬性篩選，您可以按一下 [**高級篩選**] 按鈕建立查詢。</span><span class="sxs-lookup"><span data-stu-id="b2952-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="b2952-197">您可以使用相同的活動屬性，但有下列增強功能：</span><span class="sxs-lookup"><span data-stu-id="b2952-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="b2952-198">您可以按一下 [**新增條件**]，以選取多個條件。</span><span class="sxs-lookup"><span data-stu-id="b2952-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="b2952-199">您可以選擇條件之間的**And**或**or**運算子。</span><span class="sxs-lookup"><span data-stu-id="b2952-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="b2952-200">您可以選取 [條件] 清單底部的 [**條件] 群組**專案，以形成複雜的複合條件。</span><span class="sxs-lookup"><span data-stu-id="b2952-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="b2952-201">完成作業後，請按一下 [**查詢**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="b2952-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="b2952-202">在您建立基本或高級篩選器之後，您可以使用 [**儲存查詢**] 或 [**另存查詢**] 來儲存。</span><span class="sxs-lookup"><span data-stu-id="b2952-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="b2952-203">之後，當您回到 [市場活動] 視圖時，您可以按一下 [**已儲存的查詢設定**] 載入已儲存的篩選。</span><span class="sxs-lookup"><span data-stu-id="b2952-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="b2952-204">若要匯出圖形或行銷清單，請按一下 [**匯出**]，然後選取 [**匯出圖表資料**] 或 [**匯出活動清單**]。</span><span class="sxs-lookup"><span data-stu-id="b2952-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="b2952-205">如果您有 Microsoft Defender ATP 訂閱，您可以按一下 [ **WDATP** ]，使用 MICROSOFT defender atp 連線或中斷市場活動資訊的連線。</span><span class="sxs-lookup"><span data-stu-id="b2952-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="b2952-206">如需詳細資訊，請參閱將[Office 365 atp 與 Microsoft DEFENDER Atp 整合](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="b2952-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="b2952-207">行銷活動詳細資料</span><span class="sxs-lookup"><span data-stu-id="b2952-207">Campaign details</span></span>

<span data-ttu-id="b2952-208">當您按一下市場活動的名稱時，市場活動詳細資料會出現在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="b2952-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="b2952-209">活動資訊</span><span class="sxs-lookup"><span data-stu-id="b2952-209">Campaign information</span></span>

<span data-ttu-id="b2952-210">在 [市場活動詳細資料] 視圖的頂端，可取得下列活動資訊：</span><span class="sxs-lookup"><span data-stu-id="b2952-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="b2952-211">**識別碼**：唯一的活動識別碼。</span><span class="sxs-lookup"><span data-stu-id="b2952-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="b2952-212">**開始**和**結束**：活動的開始日期和結束日期。</span><span class="sxs-lookup"><span data-stu-id="b2952-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="b2952-213">請注意，這些日期可能會比您在 [概覽] 頁面上選取的篩選日期進一步擴充。</span><span class="sxs-lookup"><span data-stu-id="b2952-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="b2952-214">**影響**：此區段包含您選取的日期範圍篩選器（或您在時程表中選取）的下列資料：</span><span class="sxs-lookup"><span data-stu-id="b2952-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="b2952-215">收件者總數。</span><span class="sxs-lookup"><span data-stu-id="b2952-215">The total number of recipients.</span></span>
  - <span data-ttu-id="b2952-216">「Inboxed」的郵件數目（也就是傳遞至收件匣，而非 [垃圾郵件] 資料夾）。</span><span class="sxs-lookup"><span data-stu-id="b2952-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="b2952-217">在網路釣魚郵件中按一下 URL 負載的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="b2952-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="b2952-218">Howe 許多使用者已訪問 URL。</span><span class="sxs-lookup"><span data-stu-id="b2952-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="b2952-219">**目標**：所計算的百分比：（組織中的活動收件者數目）/（該服務中所有組織的收件者總數）。</span><span class="sxs-lookup"><span data-stu-id="b2952-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="b2952-220">請注意，此值是透過整個市場活動的週期計算而來，而不會變更篩選日期。</span><span class="sxs-lookup"><span data-stu-id="b2952-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="b2952-221">市場活動活動的互動時程表：時程表會顯示活動的整個生命週期中的活動。</span><span class="sxs-lookup"><span data-stu-id="b2952-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="b2952-222">根據預設，陰影區域會包含您在 [概覽] 中選取的日期範圍篩選。</span><span class="sxs-lookup"><span data-stu-id="b2952-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="b2952-223">您可以按一下並拖動以選取特定的起點和終點，<u>它會變更顯示在 [**影響**] 區域中的資料，以及下一節所述的頁面的其餘</u>部分。</span><span class="sxs-lookup"><span data-stu-id="b2952-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="b2952-224">在標題列中，您可以按一下 [**下載活動] 調**高按鈕 ![ 下載活動上寫圖示， ](../../media/download-campaign-write-up-button.png) 以將市場活動詳細資料下載至 Word 檔（預設為 CampaignReport.docx）。</span><span class="sxs-lookup"><span data-stu-id="b2952-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="b2952-225">請注意，本檔包含整個市場活動生命週期的詳細資料（而不只是選取的篩選日期）。</span><span class="sxs-lookup"><span data-stu-id="b2952-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![活動資訊](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="b2952-227">行銷活動流程</span><span class="sxs-lookup"><span data-stu-id="b2952-227">Campaign flow</span></span>

<span data-ttu-id="b2952-228">在 [市場活動詳細資料] 視圖的中間，水準流程圖中的 [**流程**] 區段會顯示有關活動的重要詳細資料（稱為_Sankey_圖）。</span><span class="sxs-lookup"><span data-stu-id="b2952-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="b2952-229">這些詳細資料將協助您了解行銷活動的元素和在組織中的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="b2952-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="b2952-230">**流程圖**中所顯示的資訊是由時程表中的陰影日期範圍所控制，如上一節所述。</span><span class="sxs-lookup"><span data-stu-id="b2952-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![未包含使用者 URL 點選的行銷活動詳細資料](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="b2952-232">如果您將游標停留在圖表中的水平帶狀上，您會看到相關訊息的數量 (例如來自特定來源 IP 的訊息、來自使用特定寄件者網域來源 IP 的訊息等)。</span><span class="sxs-lookup"><span data-stu-id="b2952-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="b2952-233">圖表中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b2952-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="b2952-234">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="b2952-234">**Sender IPs**</span></span>

- <span data-ttu-id="b2952-235">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="b2952-235">**Sender domains**</span></span>

- <span data-ttu-id="b2952-236">**篩選 verdicts**：這些值與[反垃圾郵件訊息標頭](anti-spam-message-headers.md)中所述的可用網路釣魚和垃圾郵件篩選 verdicts 相關聯。</span><span class="sxs-lookup"><span data-stu-id="b2952-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="b2952-237">下表說明可用的值：</span><span class="sxs-lookup"><span data-stu-id="b2952-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="b2952-238">**值**</span><span class="sxs-lookup"><span data-stu-id="b2952-238">**Value**</span></span>|<span data-ttu-id="b2952-239">**垃圾郵件篩選判定**</span><span class="sxs-lookup"><span data-stu-id="b2952-239">**Spam filter verdict**</span></span>|<span data-ttu-id="b2952-240">**描述**</span><span class="sxs-lookup"><span data-stu-id="b2952-240">**Description**</span></span>|
  |<span data-ttu-id="b2952-241">**允許**</span><span class="sxs-lookup"><span data-stu-id="b2952-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="b2952-242">垃圾郵件篩選功能（例如郵件流程規則，也稱為傳輸規則）進行評估之前，郵件會標示為非垃圾郵件和/或略過的篩選。</span><span class="sxs-lookup"><span data-stu-id="b2952-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="b2952-243">郵件因其他原因而略過垃圾郵件篩選（例如，寄件者和收件者似乎位於相同組織中）。</span><span class="sxs-lookup"><span data-stu-id="b2952-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="b2952-244">**已封鎖**</span><span class="sxs-lookup"><span data-stu-id="b2952-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="b2952-245">垃圾郵件篩選功能（例如，依郵件流程規則）進行評估之前，郵件已標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="b2952-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="b2952-246">**已偵測**</span><span class="sxs-lookup"><span data-stu-id="b2952-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="b2952-247">垃圾郵件篩選已將郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="b2952-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="b2952-248">**未偵測到**</span><span class="sxs-lookup"><span data-stu-id="b2952-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="b2952-249">郵件已由垃圾郵件篩選標示為非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="b2952-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="b2952-250">**釋放**</span><span class="sxs-lookup"><span data-stu-id="b2952-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="b2952-251">郵件因從隔離區發行而略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="b2952-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="b2952-252">**承租人允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2952-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="b2952-253">由於反垃圾郵件原則設定，郵件會略過垃圾郵件篩選（例如，寄件者位於允許的寄件者清單或允許的網域清單中）。</span><span class="sxs-lookup"><span data-stu-id="b2952-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="b2952-254">**租使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2952-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="b2952-255">由於反垃圾郵件原則設定（例如，寄件者位於允許的寄件者清單或允許的網域清單），垃圾郵件篩選會封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="b2952-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="b2952-256">**使用者允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2952-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="b2952-257">郵件會略過垃圾郵件篩選，因為寄件者是在 Outlook 中的使用者的安全寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="b2952-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="b2952-258">**使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2952-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="b2952-259">郵件被垃圾郵件篩選封鎖，因為寄件者位於 Outlook 中使用者的封鎖寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="b2952-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="b2952-260">**幹掉**</span><span class="sxs-lookup"><span data-stu-id="b2952-260">**ZAP**</span></span>|<span data-ttu-id="b2952-261">n/a</span><span class="sxs-lookup"><span data-stu-id="b2952-261">n/a</span></span>|<span data-ttu-id="b2952-262">[零小時自動清除（ZAP）](zero-hour-auto-purge.md)會根據您的反垃圾郵件原則設定（移至 [垃圾郵件] 資料夾或「隔離」），對傳送的郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="b2952-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="b2952-263"><sup>\*</sup>請複查您的反垃圾郵件原則，因為服務可能封鎖允許的郵件。</span><span class="sxs-lookup"><span data-stu-id="b2952-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="b2952-264"><sup>\*\*</sup>請複查您的反垃圾郵件原則，因為應該隔離這些郵件，而非傳遞。</span><span class="sxs-lookup"><span data-stu-id="b2952-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="b2952-265">**傳送位置**：您可能想要調查實際傳送給收件者的訊息 (無論是移至 [收件匣] 或 [垃圾郵件] 資料夾)，即使使用者未在訊息中點選承載 URL。</span><span class="sxs-lookup"><span data-stu-id="b2952-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="b2952-266">您也可以從隔離區中移除隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="b2952-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="b2952-267">如需詳細資訊，請參閱[在 EOP 中隔離的電子郵件訊息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b2952-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="b2952-268">**已刪除資料夾**</span><span class="sxs-lookup"><span data-stu-id="b2952-268">**Deleted folder**</span></span>
  - <span data-ttu-id="b2952-269">**下降**</span><span class="sxs-lookup"><span data-stu-id="b2952-269">**Dropped**</span></span>
  - <span data-ttu-id="b2952-270">**外部**：收件者位於您的內部部署電子郵件組織中的混合式環境。</span><span class="sxs-lookup"><span data-stu-id="b2952-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="b2952-271">**失敗**</span><span class="sxs-lookup"><span data-stu-id="b2952-271">**Failed**</span></span>
  - <span data-ttu-id="b2952-272">**轉發**</span><span class="sxs-lookup"><span data-stu-id="b2952-272">**Forwarded**</span></span>
  - <span data-ttu-id="b2952-273">**收件匣**</span><span class="sxs-lookup"><span data-stu-id="b2952-273">**Inbox**</span></span>
  - <span data-ttu-id="b2952-274">**垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="b2952-274">**Junk folder**</span></span>
  - <span data-ttu-id="b2952-275">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="b2952-275">**Quarantine**</span></span>
  - <span data-ttu-id="b2952-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="b2952-276">**Unknown**</span></span>

- <span data-ttu-id="b2952-277">**URL 按一下**：這些會在下一節中說明。</span><span class="sxs-lookup"><span data-stu-id="b2952-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="b2952-278">在所有包含超過10個專案的層中，會顯示前10個專案，而其餘專案則會結合在**其他**專案中。</span><span class="sxs-lookup"><span data-stu-id="b2952-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="b2952-279">URL 點選</span><span class="sxs-lookup"><span data-stu-id="b2952-279">URL clicks</span></span>

<span data-ttu-id="b2952-280">當網路釣魚郵件傳送至收件匣或 [垃圾郵件] 資料夾時，使用者永遠都有可能會按一下 [負載 URL]。</span><span class="sxs-lookup"><span data-stu-id="b2952-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="b2952-281">未在傳送的郵件中按一下 URL 只是一項成功的衡量，但是您必須決定網路釣魚郵件在第一個位置中傳遞到其信箱的原因。</span><span class="sxs-lookup"><span data-stu-id="b2952-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="b2952-282">如果使用者按一下網路釣魚郵件中的 [負載 URL]，則動作會顯示在 [市場活動詳細資料] 視圖中圖表的 [ **URL 按一下**] 區域中。</span><span class="sxs-lookup"><span data-stu-id="b2952-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="b2952-283">**允許**</span><span class="sxs-lookup"><span data-stu-id="b2952-283">**Allowed**</span></span>

- <span data-ttu-id="b2952-284">**BlockPage**：收件者已按一下有效載荷 URL，但組織中的[ATP 安全連結](atp-safe-links.md)原則已封鎖他們對惡意網站的存取。</span><span class="sxs-lookup"><span data-stu-id="b2952-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="b2952-285">**BlockPageOverride**：收件者按一下了郵件中的 [負載 URL]，ATP 安全連結嘗試停止它們，但允許他們覆寫區塊。</span><span class="sxs-lookup"><span data-stu-id="b2952-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="b2952-286">您必須調查您的[安全連結原則](set-up-atp-safe-links-policies.md)，以瞭解使用者為何可以覆寫安全連結判定，並繼續進行惡意網站。</span><span class="sxs-lookup"><span data-stu-id="b2952-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="b2952-287">**PendingDetonationPage**： ATP 安全附件正在虛擬電腦環境中開啟的負載 URL，並查看發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="b2952-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="b2952-288">**PendingDetonationPageOverride**：收件者可以覆寫 [負載引爆] 處理常式，並開啟 URL，而不會等候結果。</span><span class="sxs-lookup"><span data-stu-id="b2952-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="b2952-289">索引標籤</span><span class="sxs-lookup"><span data-stu-id="b2952-289">Tabs</span></span>

<span data-ttu-id="b2952-290">[市場活動詳細資料] 視圖中的索引標籤可讓您進一步調查市場活動。</span><span class="sxs-lookup"><span data-stu-id="b2952-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="b2952-291">在 [[活動資訊](#campaign-information)] 區段中所述的時程表中，依陰影日期範圍所控制的索引標籤上顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="b2952-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="b2952-292">**URL 按一下**：如果使用者未按一下網路釣魚郵件中的 [負載 URL]，此區段將會是空白的。</span><span class="sxs-lookup"><span data-stu-id="b2952-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="b2952-293">如果使用者能夠按一下 URL，則會填入下列值：</span><span class="sxs-lookup"><span data-stu-id="b2952-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="b2952-294">**使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2952-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="b2952-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2952-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="b2952-296">**按一下 [時間]**</span><span class="sxs-lookup"><span data-stu-id="b2952-296">**Click time**</span></span>
  - <span data-ttu-id="b2952-297">**按一下 [判定]**</span><span class="sxs-lookup"><span data-stu-id="b2952-297">**Click verdict**</span></span>

- <span data-ttu-id="b2952-298">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="b2952-298">**Sender IPs**</span></span>

  - <span data-ttu-id="b2952-299">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2952-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="b2952-300">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="b2952-300">**Total count**</span></span>
  - <span data-ttu-id="b2952-301">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="b2952-301">**Inboxed**</span></span>
  - <span data-ttu-id="b2952-302">**非 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="b2952-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="b2952-303">已**傳遞 SPF**：寄件者[原則架構（SPF）](how-office-365-uses-spf-to-prevent-spoofing.md)已驗證寄件者。</span><span class="sxs-lookup"><span data-stu-id="b2952-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="b2952-304">未通過 SPF 驗證的寄件者表示寄件者未驗證，或郵件哄騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="b2952-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="b2952-305">**寄件者**</span><span class="sxs-lookup"><span data-stu-id="b2952-305">**Senders**</span></span>

  - <span data-ttu-id="b2952-306">**寄件者**：這是 SMTP MAIL FROM 命令中的實際寄件者位址，不一定是使用者在其電子郵件客戶程式中看到的寄件者：電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b2952-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="b2952-307">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="b2952-307">**Total count**</span></span>
  - <span data-ttu-id="b2952-308">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="b2952-308">**Inboxed**</span></span>
  - <span data-ttu-id="b2952-309">**非 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="b2952-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="b2952-310">**DKIM 通過**：寄件者是由[識別為郵件（DKIM）的網域金鑰](support-for-validation-of-dkim-signed-messages.md)所驗證。</span><span class="sxs-lookup"><span data-stu-id="b2952-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="b2952-311">未通過 DKIM 驗證的寄件者會指出未驗證寄件者，或郵件會哄騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="b2952-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="b2952-312">**DMARC 通過**：寄件者是透過以[網域為基礎的郵件驗證、報告和符合性（DMARC）](use-dmarc-to-validate-email.md)進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b2952-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="b2952-313">未通過 DMARC 驗證的寄件者會指出未驗證寄件者，或郵件會哄騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="b2952-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="b2952-314">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="b2952-314">**Attachments**</span></span>

  - <span data-ttu-id="b2952-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="b2952-315">**Filename**</span></span>
  - <span data-ttu-id="b2952-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="b2952-316">**SHA256**</span></span>
  - <span data-ttu-id="b2952-317">**惡意程式碼系列**</span><span class="sxs-lookup"><span data-stu-id="b2952-317">**Malware family**</span></span>
  - <span data-ttu-id="b2952-318">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="b2952-318">**Total count**</span></span>

- <span data-ttu-id="b2952-319">[URL]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b2952-319">**URL**</span></span>

  - <span data-ttu-id="b2952-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2952-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="b2952-321">**總數**</span><span class="sxs-lookup"><span data-stu-id="b2952-321">**Total Count**</span></span>

<span data-ttu-id="b2952-322"><sup>\*</sup> 按一下此值會開啟新的飛出畫面，其中在行銷活動詳細資料檢視上方包含更多有關指定項目 (使用者、URL 等) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b2952-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="b2952-323">若要回到行銷活動詳細資料檢視，請按一下新飛出視窗中的 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b2952-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="b2952-324">按鈕</span><span class="sxs-lookup"><span data-stu-id="b2952-324">Buttons</span></span>

<span data-ttu-id="b2952-325">行銷活動詳細資料檢視中的按鈕可讓您使用威脅瀏覽器的強大功能，進一步調查行銷活動。</span><span class="sxs-lookup"><span data-stu-id="b2952-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="b2952-326">**探索行銷活動**：使用 [行銷活動識別碼]\*\*\*\* 值做為搜尋篩選，以開啟新的威脅總管搜尋索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b2952-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="b2952-327">**探索 Inboxed 郵件**：開啟新的威脅瀏覽器搜尋索引標籤，使用**活動識別碼**及**傳遞位置：收件**匣做為搜尋篩選器。</span><span class="sxs-lookup"><span data-stu-id="b2952-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
