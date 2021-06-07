---
title: Microsoft Defender 中 Office 365 計畫的即時檢視
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 深入瞭解 Microsoft Defender 中 Office 365 的市場即時檢視。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04e3d76271e95d36d73dd473076029cb60c06900
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779440"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a4f88-103">Microsoft Defender 中 Office 365 的即時檢視</span><span class="sxs-lookup"><span data-stu-id="a4f88-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a4f88-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="a4f88-104">**Applies to**</span></span>
- [<span data-ttu-id="a4f88-105">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="a4f88-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="a4f88-106">[活動] 視圖是 Microsoft Defender 中 Office 365 方案 2 (的功能，例如，Microsoft 365 E5 或組織搭配 Office 365 Plan 2 附加元件) 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="a4f88-106">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example, Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="a4f88-107">Microsoft 365 security center 中的即時檢視會識別和分類服務中的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="a4f88-107">Campaign Views in the Microsoft 365 security center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="a4f88-108">行銷活動檢視可協助您：</span><span class="sxs-lookup"><span data-stu-id="a4f88-108">Campaign Views can help you to:</span></span>

- <span data-ttu-id="a4f88-109">更有效率地調查和回應網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="a4f88-109">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="a4f88-110">更進一步了解攻擊範圍。</span><span class="sxs-lookup"><span data-stu-id="a4f88-110">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="a4f88-111">向決策者展現價值。</span><span class="sxs-lookup"><span data-stu-id="a4f88-111">Show value to decision makers.</span></span>

<span data-ttu-id="a4f88-112">行銷活動檢視可讓您較任何人類所能夠，更快速且更完整地查看攻擊的全貌。</span><span class="sxs-lookup"><span data-stu-id="a4f88-112">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="a4f88-113">什麼是行銷活動？</span><span class="sxs-lookup"><span data-stu-id="a4f88-113">What is a campaign?</span></span>

<span data-ttu-id="a4f88-114">行銷活動是針對一或多個組織的協調式電子郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="a4f88-114">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="a4f88-115">竊取認證及公司資料的電子郵件攻擊是大型且 lucrative 的行業。</span><span class="sxs-lookup"><span data-stu-id="a4f88-115">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="a4f88-116">隨著技術不斷增加以停止攻擊的努力，攻擊者會修改其方法，以確保持續成功。</span><span class="sxs-lookup"><span data-stu-id="a4f88-116">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="a4f88-117">Microsoft 會利用整個服務中大量的反網路釣魚、反垃圾郵件和反惡意程式碼資料，協助識別市場活動。</span><span class="sxs-lookup"><span data-stu-id="a4f88-117">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="a4f88-118">我們會根據數個因素來分析和分類攻擊資訊。</span><span class="sxs-lookup"><span data-stu-id="a4f88-118">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="a4f88-119">例如：</span><span class="sxs-lookup"><span data-stu-id="a4f88-119">For example:</span></span>

- <span data-ttu-id="a4f88-120">**攻擊來源**：來源 IP 位址和寄件者電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="a4f88-120">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="a4f88-121">**郵件屬性**：郵件的內容、樣式和音調。</span><span class="sxs-lookup"><span data-stu-id="a4f88-121">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="a4f88-122">**郵件收件** 者：收件者的關聯方式。</span><span class="sxs-lookup"><span data-stu-id="a4f88-122">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="a4f88-123">例如，收件者網域、收件者工作職能 (系統管理員、行政人員等 ) 、公司類型 (大型、small、public、private、private、) 及工業。</span><span class="sxs-lookup"><span data-stu-id="a4f88-123">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="a4f88-124">**攻擊負載**：郵件中的惡意連結、附件或其他負載。</span><span class="sxs-lookup"><span data-stu-id="a4f88-124">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="a4f88-125">市場活動可能會短期，或可能跨越數天、數周或數天，具有有效和非使用中的期間。</span><span class="sxs-lookup"><span data-stu-id="a4f88-125">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="a4f88-126">您的特定組織可能會發起一個市場活動，否則您的組織可能會是多個公司的較大活動的一部分。</span><span class="sxs-lookup"><span data-stu-id="a4f88-126">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security-center"></a><span data-ttu-id="a4f88-127">安全中心的即時檢視</span><span class="sxs-lookup"><span data-stu-id="a4f88-127">Campaign Views in the security center</span></span>

<span data-ttu-id="a4f88-128">您可以在 [Microsoft 365 security center](https://security.microsoft.com)中的 **電子郵件 &** 共同作業 \> **活動**，或是直接在上使用即時檢視 <https://security.microsoft.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-128">Campaign Views is available in the [Microsoft 365 security center](https://security.microsoft.com) at **Email & collaboration** \> **Campaigns**, or directly at <https://security.microsoft.com/campaigns>.</span></span>

![Microsoft 365 security center 中的活動一覽表](../../media/campaigns-overview.png)

<span data-ttu-id="a4f88-130">您也可以從下列來源取得市場即時檢視：</span><span class="sxs-lookup"><span data-stu-id="a4f88-130">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="a4f88-131">**電子郵件 & 協同** \> 作業 **瀏覽器** \>**View** \>**活動**</span><span class="sxs-lookup"><span data-stu-id="a4f88-131">**Email & collaboration** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="a4f88-132">**電子郵件 & 協同** \> 作業 **瀏覽器** \>**View** \>**所有電子郵件** \>[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="a4f88-132">**Email & collaboration** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="a4f88-133">**電子郵件 & 協同** \> 作業 **瀏覽器** \>**View** \>**網路釣魚** \>[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="a4f88-133">**Email & collaboration** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="a4f88-134">**電子郵件 & 協同** \> 作業 **瀏覽器** \>**View** \>**惡意** \> 代碼[**活動**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="a4f88-134">**Email & collaboration** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="a4f88-135">若要存取即時檢視，您必須是「 **組織管理**」、「 **安全性管理員** **」或「安全性** 管理員」角色群組的成員，才能使用 [安全性中心]。</span><span class="sxs-lookup"><span data-stu-id="a4f88-135">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the security center.</span></span> <span data-ttu-id="a4f88-136">如需詳細資訊，請參閱[Microsoft 365 規範中心的許可權和 Microsoft 365 安全中心](permissions-microsoft-365-security-center.md)」。</span><span class="sxs-lookup"><span data-stu-id="a4f88-136">For more information, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="a4f88-137">市場活動概覽</span><span class="sxs-lookup"><span data-stu-id="a4f88-137">Campaigns overview</span></span>

<span data-ttu-id="a4f88-138">[一覽表] 頁面會顯示所有市場活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a4f88-138">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="a4f88-139">在 [預設 **市場活動** ] 索引標籤上，[ **行銷活動類型** ] 區域會顯示柱狀圖圖，顯示每日的收件者人數。</span><span class="sxs-lookup"><span data-stu-id="a4f88-139">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="a4f88-140">根據預設，圖表會顯示 **網路釣魚** 和 **惡意** 代碼資料。</span><span class="sxs-lookup"><span data-stu-id="a4f88-140">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="a4f88-141">如果您沒有看到任何活動資料，請嘗試變更日期範圍或 [篩選器](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="a4f88-141">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="a4f88-142">[一覽] 頁面上圖形下方的表格會在 [ **市場活動** ] 索引標籤上顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a4f88-142">The table below the graph on the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="a4f88-143">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a4f88-143">**Name**</span></span>

- <span data-ttu-id="a4f88-144">**樣本主旨**：行銷活動中其中一個訊息的主旨列。</span><span class="sxs-lookup"><span data-stu-id="a4f88-144">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="a4f88-145">請注意，市場活動中的所有郵件不一定會有相同的主語。</span><span class="sxs-lookup"><span data-stu-id="a4f88-145">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="a4f88-146">**目標**：所計算的百分比： (組織中的活動收件者人數) / (服務) 中所有組織的收件者總數。</span><span class="sxs-lookup"><span data-stu-id="a4f88-146">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="a4f88-147">此值會指出只有組織中的市場活動所要使用的程度 (較高的值) 比對該服務中其他組織 () 較低的值。</span><span class="sxs-lookup"><span data-stu-id="a4f88-147">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="a4f88-148">**類型**：此值為 **網路釣魚** 或 **惡意** 代碼。</span><span class="sxs-lookup"><span data-stu-id="a4f88-148">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="a4f88-149">**子類型**：此值包含有關活動的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a4f88-149">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="a4f88-150">例如：</span><span class="sxs-lookup"><span data-stu-id="a4f88-150">For example:</span></span>
  - <span data-ttu-id="a4f88-151">**網路釣魚**：在此 phished 中，您可以使用此市場活動的品牌。</span><span class="sxs-lookup"><span data-stu-id="a4f88-151">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="a4f88-152">例如，、、、 `Microsoft` `365` `Unknown` `Outlook` 或 `DocuSign` 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-152">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="a4f88-153">**惡意** 代碼：例如 `HTML/PHISH` 或 `HTML/<MalwareFamilyName>` 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-153">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="a4f88-154">在此 phished 中，您可以使用此活動的品牌。</span><span class="sxs-lookup"><span data-stu-id="a4f88-154">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="a4f88-155">當使用 Office 365 技術的 Defender 為偵測所驅動時，會將前置詞 **ATP** 新增至子類型值。</span><span class="sxs-lookup"><span data-stu-id="a4f88-155">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="a4f88-156">**收件者**：此行銷活動鎖定的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="a4f88-156">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="a4f88-157">**Inboxed**：從其收件匣的此項活動接收郵件的使用者人數 (未傳遞到其 [垃圾郵件] 資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-157">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="a4f88-158">按下：在網路釣魚郵件中 **，按一下 URL** 或開啟附件的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="a4f88-158">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="a4f88-159">**按一下 [速率**：由「已 **按一下** Inboxed」所計算的百分比  /  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a4f88-159">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="a4f88-160">此值是活動之效能的指示器。</span><span class="sxs-lookup"><span data-stu-id="a4f88-160">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="a4f88-161">換句話說，如果收件者能夠將郵件識別為網路釣魚，而且沒有按一下 [負載 URL]。</span><span class="sxs-lookup"><span data-stu-id="a4f88-161">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="a4f88-162">請注意，惡意程式碼活動中不會使用 **點擊比率** 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-162">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="a4f88-163">已 **訪問**：有多少使用者實際將其設為 [負載] 網站。</span><span class="sxs-lookup"><span data-stu-id="a4f88-163">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="a4f88-164">如果有 **按一下** 的值，但安全連結已封鎖網站的存取權，這個值將會是零。</span><span class="sxs-lookup"><span data-stu-id="a4f88-164">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="a4f88-165">[ **市場活動來源** ] 索引標籤會顯示世界地圖上的郵件來源。</span><span class="sxs-lookup"><span data-stu-id="a4f88-165">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="a4f88-166">篩選和設定</span><span class="sxs-lookup"><span data-stu-id="a4f88-166">Filters and settings</span></span>

<span data-ttu-id="a4f88-167">在 [ **活動** ] 頁面的頂端，有數個篩選和查詢設定可協助您找出並隔離特定的市場活動。</span><span class="sxs-lookup"><span data-stu-id="a4f88-167">At the top of the **Campaign** page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![市場活動篩選](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="a4f88-169">您可以執行的最基本篩選為開始日期/時間和結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a4f88-169">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="a4f88-170">若要進一步篩選視圖，您可以使用多個值篩選的單一屬性，方法是按一下 [**行銷活動類型**] 按鈕，進行選取，然後按一下 [重新整理 **]。**</span><span class="sxs-lookup"><span data-stu-id="a4f88-170">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="a4f88-171">下列清單說明「 **行銷活動類型** 」按鈕中可用的可篩選的活動屬性：</span><span class="sxs-lookup"><span data-stu-id="a4f88-171">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="a4f88-172">**基本**：</span><span class="sxs-lookup"><span data-stu-id="a4f88-172">**Basic**:</span></span>
  - <span data-ttu-id="a4f88-173">**行銷活動類型**：選取 **惡意** 代碼或 **網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="a4f88-173">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="a4f88-174">清除選取範圍與同時選取這兩者的結果相同。</span><span class="sxs-lookup"><span data-stu-id="a4f88-174">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="a4f88-175">**市場活動名稱**</span><span class="sxs-lookup"><span data-stu-id="a4f88-175">**Campaign name**</span></span>
  - <span data-ttu-id="a4f88-176">**活動子類型**</span><span class="sxs-lookup"><span data-stu-id="a4f88-176">**Campaign subtype**</span></span>
  - <span data-ttu-id="a4f88-177">**Sender**</span><span class="sxs-lookup"><span data-stu-id="a4f88-177">**Sender**</span></span>
  - <span data-ttu-id="a4f88-178">**收件者**</span><span class="sxs-lookup"><span data-stu-id="a4f88-178">**Recipients**</span></span>
  - <span data-ttu-id="a4f88-179">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="a4f88-179">**Sender domain**</span></span>
  - <span data-ttu-id="a4f88-180">**主旨**</span><span class="sxs-lookup"><span data-stu-id="a4f88-180">**Subject**</span></span>
  - <span data-ttu-id="a4f88-181">**附件檔名**</span><span class="sxs-lookup"><span data-stu-id="a4f88-181">**Attachment filename**</span></span>
  - <span data-ttu-id="a4f88-182">**惡意程式碼系列**</span><span class="sxs-lookup"><span data-stu-id="a4f88-182">**Malware family**</span></span>
  - <span data-ttu-id="a4f88-183">**標記**：已套用指定使用者標記的使用者或群組 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-183">**Tags**: Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="a4f88-184">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="a4f88-184">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="a4f88-185">**傳遞動作**</span><span class="sxs-lookup"><span data-stu-id="a4f88-185">**Delivery action**</span></span>
  - <span data-ttu-id="a4f88-186">**其他動作**</span><span class="sxs-lookup"><span data-stu-id="a4f88-186">**Additional action**</span></span>
  - <span data-ttu-id="a4f88-187">**方向性**</span><span class="sxs-lookup"><span data-stu-id="a4f88-187">**Directionality**</span></span>
  - <span data-ttu-id="a4f88-188">**偵測技術**</span><span class="sxs-lookup"><span data-stu-id="a4f88-188">**Detection technology**</span></span>
  - <span data-ttu-id="a4f88-189">**原始傳遞位置**</span><span class="sxs-lookup"><span data-stu-id="a4f88-189">**Original delivery location**</span></span>
  - <span data-ttu-id="a4f88-190">**最新傳遞位置**</span><span class="sxs-lookup"><span data-stu-id="a4f88-190">**Latest delivery location**</span></span>
  - <span data-ttu-id="a4f88-191">**系統覆寫**</span><span class="sxs-lookup"><span data-stu-id="a4f88-191">**System overrides**</span></span>

- <span data-ttu-id="a4f88-192">**Advanced**：</span><span class="sxs-lookup"><span data-stu-id="a4f88-192">**Advanced**:</span></span>
  - <span data-ttu-id="a4f88-193">**網際網路郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中提供。</span><span class="sxs-lookup"><span data-stu-id="a4f88-193">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="a4f88-194">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-194">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="a4f88-195">**網路消息識別碼**：在郵件頭的 [ **X-MS-Exchange-Organization-網路 Message-Id** 標頭] 欄位中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="a4f88-195">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="a4f88-196">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="a4f88-196">**Sender IP**</span></span>
  - <span data-ttu-id="a4f88-197">**附件 SHA256**：若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令： `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-197">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="a4f88-198">**叢集識別碼**</span><span class="sxs-lookup"><span data-stu-id="a4f88-198">**Cluster ID**</span></span>
  - <span data-ttu-id="a4f88-199">**警示識別碼**</span><span class="sxs-lookup"><span data-stu-id="a4f88-199">**Alert ID**</span></span>
  - <span data-ttu-id="a4f88-200">**警示原則識別碼**</span><span class="sxs-lookup"><span data-stu-id="a4f88-200">**Alert Policy ID**</span></span>
  - <span data-ttu-id="a4f88-201">**活動識別碼**</span><span class="sxs-lookup"><span data-stu-id="a4f88-201">**Campaign ID**</span></span>
  - <span data-ttu-id="a4f88-202">**ZAP URL 信號**</span><span class="sxs-lookup"><span data-stu-id="a4f88-202">**ZAP URL signal**</span></span>

- <span data-ttu-id="a4f88-203">**URLs**：</span><span class="sxs-lookup"><span data-stu-id="a4f88-203">**URLs**:</span></span>
  - <span data-ttu-id="a4f88-204">**URL 網域**</span><span class="sxs-lookup"><span data-stu-id="a4f88-204">**URL domain**</span></span>
  - <span data-ttu-id="a4f88-205">**URL 網域和路徑**</span><span class="sxs-lookup"><span data-stu-id="a4f88-205">**URL domain and path**</span></span>
  - <span data-ttu-id="a4f88-206">**URL**</span><span class="sxs-lookup"><span data-stu-id="a4f88-206">**URL**</span></span>
  - <span data-ttu-id="a4f88-207">**URL 路徑**</span><span class="sxs-lookup"><span data-stu-id="a4f88-207">**URL path**</span></span>
  - <span data-ttu-id="a4f88-208">**按一下 [判定]**</span><span class="sxs-lookup"><span data-stu-id="a4f88-208">**Click verdict**</span></span>

<span data-ttu-id="a4f88-209">如需更多的高級篩選，包括多個屬性篩選，您可以按一下 [ **高級篩選** ] 按鈕建立查詢。</span><span class="sxs-lookup"><span data-stu-id="a4f88-209">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="a4f88-210">您可以使用相同的活動屬性，但有下列增強功能：</span><span class="sxs-lookup"><span data-stu-id="a4f88-210">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="a4f88-211">您可以按一下 [ **新增條件** ]，以選取多個條件。</span><span class="sxs-lookup"><span data-stu-id="a4f88-211">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="a4f88-212">您可以選擇條件之間的 **And** 或 **or** 運算子。</span><span class="sxs-lookup"><span data-stu-id="a4f88-212">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="a4f88-213">您可以選取 [條件] 清單底部的 [ **條件] 群組** 專案，以形成複雜的複合條件。</span><span class="sxs-lookup"><span data-stu-id="a4f88-213">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="a4f88-214">完成作業後，請按一下 [ **查詢** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a4f88-214">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="a4f88-215">在您建立基本或高級篩選器之後，您可以使用 [ **儲存查詢** ] 或 [ **另存查詢**] 來儲存。</span><span class="sxs-lookup"><span data-stu-id="a4f88-215">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="a4f88-216">之後，當您回到 [ **市場活動** ] 頁面時，您可以按一下 [ **已儲存的查詢設定**] 載入已儲存的篩選。</span><span class="sxs-lookup"><span data-stu-id="a4f88-216">Later, when you return to the **Campaigns** page, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="a4f88-217">若要匯出圖形或行銷清單，請按一下 [ **匯出** ]，然後選取 [ **匯出圖表資料** ] 或 [ **匯出活動清單**]。</span><span class="sxs-lookup"><span data-stu-id="a4f88-217">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="a4f88-218">如果您有 microsoft defender for endpoint 訂閱，您可以按一下 [ **MDE 設定**，使用 microsoft defender for endpoint 來連線或中斷市場活動資訊的連線。</span><span class="sxs-lookup"><span data-stu-id="a4f88-218">If you have a Microsoft Defender for Endpoint subscription, you can click **MDE Settings** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a4f88-219">如需詳細資訊，請參閱[整合 microsoft defender for Office 365 搭配 microsoft defender for Endpoint](integrate-office-365-ti-with-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="a4f88-219">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="a4f88-220">行銷活動詳細資料</span><span class="sxs-lookup"><span data-stu-id="a4f88-220">Campaign details</span></span>

<span data-ttu-id="a4f88-221">當您按一下市場活動的名稱時，市場活動詳細資料會出現在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="a4f88-221">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="a4f88-222">活動資訊</span><span class="sxs-lookup"><span data-stu-id="a4f88-222">Campaign information</span></span>

<span data-ttu-id="a4f88-223">在 [市場活動詳細資料] 視圖的頂端，可取得下列活動資訊：</span><span class="sxs-lookup"><span data-stu-id="a4f88-223">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="a4f88-224">**活動** 識別碼：唯一的活動識別碼。</span><span class="sxs-lookup"><span data-stu-id="a4f88-224">**Campaign ID**: The unique campaign identifier.</span></span>
- <span data-ttu-id="a4f88-225">**活動**：活動的工期和活動。</span><span class="sxs-lookup"><span data-stu-id="a4f88-225">**Activity**: The duration and activity of the campaign.</span></span>
- <span data-ttu-id="a4f88-226">您在 [時程表) ] 中選取的日期範圍篩選器的下列資料 (：</span><span class="sxs-lookup"><span data-stu-id="a4f88-226">The following data for the date range filter you selected (or that you select in the timeline):</span></span>
- <span data-ttu-id="a4f88-227">**影響**</span><span class="sxs-lookup"><span data-stu-id="a4f88-227">**Impact**</span></span>
- <span data-ttu-id="a4f88-228">**郵件**：收件者總數。</span><span class="sxs-lookup"><span data-stu-id="a4f88-228">**Messages**: The total number of recipients.</span></span>
- <span data-ttu-id="a4f88-229">**Inboxed**：已傳遞至 [收件匣] 的郵件數目，而非 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a4f88-229">**Inboxed**: The number of messages that were delivered to the Inbox, not to the Junk Email folder.</span></span>
- <span data-ttu-id="a4f88-230">已 **按一下 [連結**]：在網路釣魚郵件中按一下 URL 負載的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="a4f88-230">**Clicked link**: How many users clicked on the URL payload in the phishing message.</span></span>
- <span data-ttu-id="a4f88-231">已 **訪問的連結**：有多少使用者已訪問 URL。</span><span class="sxs-lookup"><span data-stu-id="a4f88-231">**Visited link**: How many users visited the URL.</span></span>
- <span data-ttu-id="a4f88-232">**目標 (% )**：所計算的百分比： (組織中的活動收件者數目) / (服務) 中所有組織的收件者總數。</span><span class="sxs-lookup"><span data-stu-id="a4f88-232">**Targeted(%)**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="a4f88-233">請注意，此值是透過整個活動週期計算的，而不會根據日期篩選器而變更。</span><span class="sxs-lookup"><span data-stu-id="a4f88-233">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>
- <span data-ttu-id="a4f88-234">開始日期/時間和結束市場活動流程的資料/時間篩選，如下一節所述。</span><span class="sxs-lookup"><span data-stu-id="a4f88-234">Start date/time and end data/time filters for the campaign flow as described in the next section.</span></span>
- <span data-ttu-id="a4f88-235">市場活動活動的互動時程表：時程表會顯示活動的整個生命週期中的活動。</span><span class="sxs-lookup"><span data-stu-id="a4f88-235">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="a4f88-236">您可以將游標移到圖表中的資料點，以查看偵測到的郵件數量。</span><span class="sxs-lookup"><span data-stu-id="a4f88-236">You can hover over the data points in the graph to see the amount of detected messages.</span></span>

![活動資訊](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="a4f88-238">行銷活動流程</span><span class="sxs-lookup"><span data-stu-id="a4f88-238">Campaign flow</span></span>

<span data-ttu-id="a4f88-239">在 [市場活動詳細資料] 視圖中，市場活動的重要詳細資料會呈現在水準流程圖中 (稱為 _Sankey_ 圖表) 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-239">In the middle of the campaign details view, important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="a4f88-240">這些詳細資料將協助您了解行銷活動的元素和在組織中的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="a4f88-240">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="a4f88-241">流程圖中所顯示的資訊是由時程表中的日期範圍篩選所控制，如上一節所述。</span><span class="sxs-lookup"><span data-stu-id="a4f88-241">The information that's displayed in the flow diagram is controlled by the date range filter in the timeline as described in the previous section.</span></span>

![未包含使用者 URL 點選的行銷活動詳細資料](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="a4f88-243">如果您將游標停留在圖表中的水平帶狀上，您會看到相關訊息的數量 (例如來自特定來源 IP 的訊息、來自使用特定寄件者網域來源 IP 的訊息等)。</span><span class="sxs-lookup"><span data-stu-id="a4f88-243">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="a4f88-244">圖表中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a4f88-244">The diagram contains the following information:</span></span>

- <span data-ttu-id="a4f88-245">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="a4f88-245">**Sender IPs**</span></span>
- <span data-ttu-id="a4f88-246">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="a4f88-246">**Sender domains**</span></span>
- <span data-ttu-id="a4f88-247">**篩選 verdicts**：值與 [反垃圾郵件郵件頭](anti-spam-message-headers.md)中所述的可用網路釣魚和垃圾郵件篩選 verdicts 有關。</span><span class="sxs-lookup"><span data-stu-id="a4f88-247">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="a4f88-248">下表說明可用的值：</span><span class="sxs-lookup"><span data-stu-id="a4f88-248">The available values are described in the following table:</span></span>

  <br>

  ****

  |<span data-ttu-id="a4f88-249">值</span><span class="sxs-lookup"><span data-stu-id="a4f88-249">Value</span></span>|<span data-ttu-id="a4f88-250">垃圾郵件篩選判定</span><span class="sxs-lookup"><span data-stu-id="a4f88-250">Spam filter verdict</span></span>|<span data-ttu-id="a4f88-251">描述</span><span class="sxs-lookup"><span data-stu-id="a4f88-251">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="a4f88-252">**允許**</span><span class="sxs-lookup"><span data-stu-id="a4f88-252">**Allowed**</span></span>|`SFV:SKN` <p> `SFV:SKI`|<span data-ttu-id="a4f88-253">垃圾郵件篩選評估之前，郵件已標示為非垃圾郵件和/或略過的篩選。</span><span class="sxs-lookup"><span data-stu-id="a4f88-253">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="a4f88-254">例如，郵件流程規則（也稱為傳輸規則) ）將郵件標示為非垃圾郵件 (。</span><span class="sxs-lookup"><span data-stu-id="a4f88-254">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span> <p> <span data-ttu-id="a4f88-255">郵件因其他原因而略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="a4f88-255">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="a4f88-256">例如，寄件者和收件者似乎位於相同組織中。</span><span class="sxs-lookup"><span data-stu-id="a4f88-256">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="a4f88-257">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="a4f88-257">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="a4f88-258">垃圾郵件篩選評估之前，郵件已標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="a4f88-258">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="a4f88-259">例如，依郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="a4f88-259">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="a4f88-260">**已偵測**</span><span class="sxs-lookup"><span data-stu-id="a4f88-260">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="a4f88-261">垃圾郵件篩選已將此郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="a4f88-261">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="a4f88-262">**未偵測到**</span><span class="sxs-lookup"><span data-stu-id="a4f88-262">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="a4f88-263">郵件已由垃圾郵件篩選標示為非垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="a4f88-263">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="a4f88-264">**釋放**</span><span class="sxs-lookup"><span data-stu-id="a4f88-264">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="a4f88-265">郵件因從隔離區發行而略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="a4f88-265">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="a4f88-266">**承租人允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4f88-266">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="a4f88-267">由於反垃圾郵件原則中的設定，郵件會略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="a4f88-267">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="a4f88-268">例如，寄件者位於允許的寄件者清單或允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="a4f88-268">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="a4f88-269">**租使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4f88-269">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="a4f88-270">由於反垃圾郵件原則中的設定，郵件已被垃圾郵件篩選封鎖。</span><span class="sxs-lookup"><span data-stu-id="a4f88-270">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="a4f88-271">例如，寄件者位於允許的寄件者清單或允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="a4f88-271">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="a4f88-272">**使用者允許**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4f88-272">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="a4f88-273">因為寄件者位於使用者的安全寄件者清單中，郵件會略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="a4f88-273">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="a4f88-274">**使用者區塊**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4f88-274">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="a4f88-275">郵件被垃圾郵件篩選封鎖，因為寄件者是在使用者的封鎖寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="a4f88-275">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="a4f88-276">**幹掉**</span><span class="sxs-lookup"><span data-stu-id="a4f88-276">**ZAP**</span></span>|<span data-ttu-id="a4f88-277">不適用</span><span class="sxs-lookup"><span data-stu-id="a4f88-277">n/a</span></span>|<span data-ttu-id="a4f88-278">[零小時自動清除 (ZAP) ](zero-hour-auto-purge.md) 將傳遞的郵件移至 [垃圾郵件] 資料夾或隔離區。</span><span class="sxs-lookup"><span data-stu-id="a4f88-278">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="a4f88-279">您可以設定反垃圾郵件原則中的動作。</span><span class="sxs-lookup"><span data-stu-id="a4f88-279">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="a4f88-280"><sup>\*</sup> 請複查您的反垃圾郵件原則，因為服務可能封鎖允許的郵件。</span><span class="sxs-lookup"><span data-stu-id="a4f88-280"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="a4f88-281"><sup>\*\*</sup> 請複查您的反垃圾郵件原則，因為應該隔離這些郵件，而非傳遞。</span><span class="sxs-lookup"><span data-stu-id="a4f88-281"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="a4f88-282">**郵件目的地**：您可能想要調查傳送給收件者的郵件 (至收件匣或 [垃圾郵件] 資料夾) ，即使使用者未按一下郵件中的 [載荷] URL 也是一樣。</span><span class="sxs-lookup"><span data-stu-id="a4f88-282">**Message destinations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="a4f88-283">您也可以從隔離區中移除隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="a4f88-283">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="a4f88-284">如需詳細資訊，請參閱 [在 EOP 中隔離的電子郵件訊息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a4f88-284">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="a4f88-285">**已刪除資料夾**</span><span class="sxs-lookup"><span data-stu-id="a4f88-285">**Deleted folder**</span></span>
  - <span data-ttu-id="a4f88-286">**下降**</span><span class="sxs-lookup"><span data-stu-id="a4f88-286">**Dropped**</span></span>
  - <span data-ttu-id="a4f88-287">**外部**：收件者位於您的內部部署電子郵件組織中的混合式環境。</span><span class="sxs-lookup"><span data-stu-id="a4f88-287">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="a4f88-288">**已失敗**</span><span class="sxs-lookup"><span data-stu-id="a4f88-288">**Failed**</span></span>
  - <span data-ttu-id="a4f88-289">**轉發**</span><span class="sxs-lookup"><span data-stu-id="a4f88-289">**Forwarded**</span></span>
  - <span data-ttu-id="a4f88-290">**收件匣**</span><span class="sxs-lookup"><span data-stu-id="a4f88-290">**Inbox**</span></span>
  - <span data-ttu-id="a4f88-291">**垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="a4f88-291">**Junk folder**</span></span>
  - <span data-ttu-id="a4f88-292">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="a4f88-292">**Quarantine**</span></span>
  - <span data-ttu-id="a4f88-293">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="a4f88-293">**Unknown**</span></span>

- <span data-ttu-id="a4f88-294">**URL 按一下**：這些值會在下一節中說明。</span><span class="sxs-lookup"><span data-stu-id="a4f88-294">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="a4f88-295">在所有包含超過10個專案的層中，會顯示前10個專案，而其餘專案則會結合在 **其他** 專案中。</span><span class="sxs-lookup"><span data-stu-id="a4f88-295">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="a4f88-296">URL 點選</span><span class="sxs-lookup"><span data-stu-id="a4f88-296">URL clicks</span></span>

<span data-ttu-id="a4f88-297">當仿冒郵件傳送至收件者的收件匣或 [垃圾郵件] 資料夾時，使用者永遠都有可能會按一下 [負載 URL]。</span><span class="sxs-lookup"><span data-stu-id="a4f88-297">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="a4f88-298">不是按一下 URL 是一項很小的成功，但是您必須決定網路釣魚郵件甚至傳遞到信箱的原因。</span><span class="sxs-lookup"><span data-stu-id="a4f88-298">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="a4f88-299">如果使用者按一下網路釣魚郵件中的 [負載 URL]，則動作會顯示在 [市場活動詳細資料] 視圖中圖表的 [ **URL 按一下** ] 區域中。</span><span class="sxs-lookup"><span data-stu-id="a4f88-299">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="a4f88-300">**允許**</span><span class="sxs-lookup"><span data-stu-id="a4f88-300">**Allowed**</span></span>
- <span data-ttu-id="a4f88-301">**BlockPage**：收件者已按一下有效載荷 URL，但組織中的 [安全連結](safe-links.md) 原則已封鎖其對惡意網站的存取。</span><span class="sxs-lookup"><span data-stu-id="a4f88-301">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="a4f88-302">**BlockPageOverride**：收件者按一下了郵件中的 [負載 URL]，則安全連結會嘗試將其停止，但允許覆寫區塊。</span><span class="sxs-lookup"><span data-stu-id="a4f88-302">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="a4f88-303">檢查您的 [安全連結原則](set-up-safe-links-policies.md) ，以瞭解使用者為何可以覆寫安全連結判定，並繼續進行惡意網站。</span><span class="sxs-lookup"><span data-stu-id="a4f88-303">Inspect your [Safe Links policies](set-up-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="a4f88-304">**PendingDetonationPage**： Microsoft Defender for Office 365 中的安全附件是在虛擬電腦環境中開啟及調查負載 URL 的過程中。</span><span class="sxs-lookup"><span data-stu-id="a4f88-304">**PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="a4f88-305">**PendingDetonationPageOverride**：收件者可以覆寫 [負載引爆] 處理常式，並開啟 URL，而不會等候結果。</span><span class="sxs-lookup"><span data-stu-id="a4f88-305">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="a4f88-306">索引標籤</span><span class="sxs-lookup"><span data-stu-id="a4f88-306">Tabs</span></span>

<span data-ttu-id="a4f88-307">[市場活動詳細資料] 視圖中的索引標籤可讓您進一步調查市場活動。</span><span class="sxs-lookup"><span data-stu-id="a4f88-307">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="a4f88-308">在 [ [活動資訊](#campaign-information) ] 區段中所述的時程表中，以 [日期範圍] 篩選所控制的索引標籤上顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4f88-308">The information that's displayed on the tabs is controlled by the date range filter in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="a4f88-309">**URL 按一下**：如果使用者沒有按一下郵件中的 [負載 URL]，此區段將會是空白的。</span><span class="sxs-lookup"><span data-stu-id="a4f88-309">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="a4f88-310">如果使用者能夠按一下 URL，則會填入下列值：</span><span class="sxs-lookup"><span data-stu-id="a4f88-310">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="a4f88-311">**使用者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4f88-311">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="a4f88-312">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4f88-312">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="a4f88-313">**按一下 [時間]**</span><span class="sxs-lookup"><span data-stu-id="a4f88-313">**Click time**</span></span>
  - <span data-ttu-id="a4f88-314">**按一下 [判定]**</span><span class="sxs-lookup"><span data-stu-id="a4f88-314">**Click verdict**</span></span>

- <span data-ttu-id="a4f88-315">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="a4f88-315">**Sender IPs**</span></span>
  - <span data-ttu-id="a4f88-316">**寄件者 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4f88-316">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="a4f88-317">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="a4f88-317">**Total count**</span></span>
  - <span data-ttu-id="a4f88-318">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="a4f88-318">**Inboxed**</span></span>
  - <span data-ttu-id="a4f88-319">**非 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="a4f88-319">**Not Inboxed**</span></span>
  - <span data-ttu-id="a4f88-320">已 **通過的 SPF**：寄件者 [原則框架 (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)驗證寄件者。</span><span class="sxs-lookup"><span data-stu-id="a4f88-320">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="a4f88-321">未通過 SPF 驗證的寄件者表示未驗證寄件者，或郵件是哄騙合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="a4f88-321">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="a4f88-322">**寄件者**</span><span class="sxs-lookup"><span data-stu-id="a4f88-322">**Senders**</span></span>
  - <span data-ttu-id="a4f88-323">**寄件者**：這是 SMTP MAIL FROM 命令中的實際寄件者位址，不一定是使用者在其電子郵件客戶程式中看到的寄件者：電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a4f88-323">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="a4f88-324">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="a4f88-324">**Total count**</span></span>
  - <span data-ttu-id="a4f88-325">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="a4f88-325">**Inboxed**</span></span>
  - <span data-ttu-id="a4f88-326">**非 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="a4f88-326">**Not Inboxed**</span></span>
  - <span data-ttu-id="a4f88-327">**DKIM 通過**：寄件者是由 [識別為郵件 (DKIM) 的網域金鑰](support-for-validation-of-dkim-signed-messages.md)所驗證。</span><span class="sxs-lookup"><span data-stu-id="a4f88-327">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="a4f88-328">未通過 DKIM 驗證的寄件者表示未驗證寄件者，或郵件為偽造合法寄件者。</span><span class="sxs-lookup"><span data-stu-id="a4f88-328">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="a4f88-329">已 **通過 DMARC**：寄件者是透過以 [網域為基礎的郵件驗證、報告和一致性 (DMARC)](use-dmarc-to-validate-email.md)進行驗證。</span><span class="sxs-lookup"><span data-stu-id="a4f88-329">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="a4f88-330">未通過 DMARC 驗證的寄件者表示未驗證寄件者，或郵件為偽造合法寄件者。</span><span class="sxs-lookup"><span data-stu-id="a4f88-330">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="a4f88-331">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="a4f88-331">**Attachments**</span></span>
  - <span data-ttu-id="a4f88-332">**Filename**</span><span class="sxs-lookup"><span data-stu-id="a4f88-332">**Filename**</span></span>
  - <span data-ttu-id="a4f88-333">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="a4f88-333">**SHA256**</span></span>
  - <span data-ttu-id="a4f88-334">**惡意程式碼系列**</span><span class="sxs-lookup"><span data-stu-id="a4f88-334">**Malware family**</span></span>
  - <span data-ttu-id="a4f88-335">**總計計數**</span><span class="sxs-lookup"><span data-stu-id="a4f88-335">**Total count**</span></span>

- <span data-ttu-id="a4f88-336">**URL**</span><span class="sxs-lookup"><span data-stu-id="a4f88-336">**URL**</span></span>
  - <span data-ttu-id="a4f88-337">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4f88-337">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="a4f88-338">**總數**</span><span class="sxs-lookup"><span data-stu-id="a4f88-338">**Total Count**</span></span>

<span data-ttu-id="a4f88-339"><sup>\*</sup> 按一下此值會開啟新的飛出畫面，其中在行銷活動詳細資料檢視上方包含更多有關指定項目 (使用者、URL 等) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a4f88-339"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="a4f88-340">若要回到行銷活動詳細資料檢視，請按一下新飛出視窗中的 [完成]。</span><span class="sxs-lookup"><span data-stu-id="a4f88-340">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="a4f88-341">按鈕</span><span class="sxs-lookup"><span data-stu-id="a4f88-341">Buttons</span></span>

<span data-ttu-id="a4f88-342">[市場活動詳細資料] 視圖底部的按鈕可讓您調查和記錄有關活動的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="a4f88-342">The buttons at the bottom the campaign details view allow you to investigate and record details about the campaign:</span></span>

- <span data-ttu-id="a4f88-343">**探索郵件**：使用威脅瀏覽器的威力進一步調查市場活動：</span><span class="sxs-lookup"><span data-stu-id="a4f88-343">**Explore messages**: Use the power of Threat Explorer to further investigate the campaign:</span></span>
  - <span data-ttu-id="a4f88-344">**所有郵件**：開啟新的威脅瀏覽器搜尋索引標籤，使用 [ **活動識別碼** ] 值作為搜尋篩選器。</span><span class="sxs-lookup"><span data-stu-id="a4f88-344">**All messages**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
  - <span data-ttu-id="a4f88-345">**Inboxed 郵件**：開啟新的威脅瀏覽器搜尋索引標籤，使用 [ **活動識別碼** ] 和 [ **傳遞位置：] [收件** 匣] 作為搜尋篩選器。</span><span class="sxs-lookup"><span data-stu-id="a4f88-345">**Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
  - <span data-ttu-id="a4f88-346">**內部郵件**：開啟新的威脅瀏覽器搜尋索引標籤，使用 **活動識別碼** 和 **方向性：組織內部** 為搜尋篩選。</span><span class="sxs-lookup"><span data-stu-id="a4f88-346">**Internal messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Directionality: Intra-org** as the search filter.</span></span>

- <span data-ttu-id="a4f88-347">**下載威脅報告**：將市場活動詳細資料下載至 Word 檔 (預設會以名為 CampaignReport.docx) 。</span><span class="sxs-lookup"><span data-stu-id="a4f88-347">**Download threat report**: Download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="a4f88-348">請注意，下載包含整個市場活動的整個生命週期的詳細資料，而不只是 (您) 所選取的篩選日期。</span><span class="sxs-lookup"><span data-stu-id="a4f88-348">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>
