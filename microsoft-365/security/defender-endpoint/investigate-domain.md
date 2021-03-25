---
title: 調查 Microsoft Defender 的端點網域
description: 使用調查選項，查看裝置和伺服器是否已與惡意網域進行通訊。
keywords: 調查網域、網域、惡意網域、microsoft defender atp、警示、URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7918a62c3afa2cfd97ffc77ad756339010c1d7a3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186074"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="23320-104">調查與 Microsoft Defender for Endpoint alert 相關聯的網域</span><span class="sxs-lookup"><span data-stu-id="23320-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="23320-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="23320-105">**Applies to:**</span></span>
- [<span data-ttu-id="23320-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="23320-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="23320-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23320-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="23320-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="23320-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23320-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="23320-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="23320-110">調查網域，以查看商業網路中的裝置和伺服器是否已與已知惡意的網域進行通訊。</span><span class="sxs-lookup"><span data-stu-id="23320-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="23320-111">您可以使用搜尋功能，或按一下 **裝置時程表** 中的網域連結，調查網域。</span><span class="sxs-lookup"><span data-stu-id="23320-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="23320-112">您可以在 URL 視圖中看到下列各節中的資訊：</span><span class="sxs-lookup"><span data-stu-id="23320-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="23320-113">URL 詳細資料、連絡人、名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="23320-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="23320-114">與此 URL 相關的警示</span><span class="sxs-lookup"><span data-stu-id="23320-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="23320-115">組織中的 URL</span><span class="sxs-lookup"><span data-stu-id="23320-115">URL in organization</span></span>
- <span data-ttu-id="23320-116">最近透過 URL 觀察到的裝置</span><span class="sxs-lookup"><span data-stu-id="23320-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="23320-117">全球 URL</span><span class="sxs-lookup"><span data-stu-id="23320-117">URL worldwide</span></span>

<span data-ttu-id="23320-118">「 **全球 url** 」一節列出 Url、Whois 的進一步詳細資料、相關開啟的事件數目，以及作用中警示的數目。</span><span class="sxs-lookup"><span data-stu-id="23320-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="23320-119">事件</span><span class="sxs-lookup"><span data-stu-id="23320-119">Incident</span></span>

<span data-ttu-id="23320-120">**事件** 卡片會顯示過去180天事件中所有活動警示的橫條圖。</span><span class="sxs-lookup"><span data-stu-id="23320-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="23320-121">流行</span><span class="sxs-lookup"><span data-stu-id="23320-121">Prevalence</span></span>

<span data-ttu-id="23320-122">「 **傳播** 卡片」提供組織內的 URL 的詳細資訊，在指定的一段時間內。</span><span class="sxs-lookup"><span data-stu-id="23320-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="23320-123">雖然預設時段是過去30天，您可以選取卡片一角的向下箭號，即可自訂範圍。</span><span class="sxs-lookup"><span data-stu-id="23320-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="23320-124">可使用的最短範圍是過去一天的流行，而最長的範圍則是過去6個月。</span><span class="sxs-lookup"><span data-stu-id="23320-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="23320-125">警示</span><span class="sxs-lookup"><span data-stu-id="23320-125">Alerts</span></span>

<span data-ttu-id="23320-126">[ **警示** ] 索引標籤提供與 URL 相關聯的警示清單。</span><span class="sxs-lookup"><span data-stu-id="23320-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="23320-127">這裡顯示的表格是警示佇列畫面上顯示之警示的篩選版本，只顯示與網域相關聯的警示、嚴重性、狀態、關聯的事件、分類、調查狀態等等。</span><span class="sxs-lookup"><span data-stu-id="23320-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="23320-128">您可以從欄標題上方的 [動作] 功能表中，選取 [ **自訂資料行** ]，以顯示更多或更少的資訊。</span><span class="sxs-lookup"><span data-stu-id="23320-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="23320-129">您也可以透過在相同功能表上選取 [ **每頁的專案** ] 來調整顯示的專案數。</span><span class="sxs-lookup"><span data-stu-id="23320-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="23320-130">組織中的觀測</span><span class="sxs-lookup"><span data-stu-id="23320-130">Observed in organization</span></span>

<span data-ttu-id="23320-131">在 [ **組織中看到** 的] 索引標籤會在 URL 上看到的事件及相關警示上，提供按時間排序的視圖。</span><span class="sxs-lookup"><span data-stu-id="23320-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="23320-132">此索引標籤包含時程表及可自訂的表格，其中列出事件詳細資料，例如時間、裝置及發生狀況的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="23320-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="23320-133">您可以在表格標題上方的文字欄位中輸入日期，以查看不同時間週期中的事件。</span><span class="sxs-lookup"><span data-stu-id="23320-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="23320-134">您也可以選擇不同的時程表區域，以自訂時間範圍。</span><span class="sxs-lookup"><span data-stu-id="23320-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="23320-135">**調查網域：**</span><span class="sxs-lookup"><span data-stu-id="23320-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="23320-136">從 **搜尋** 列下拉式功能表中選取 [ **URL** ]。</span><span class="sxs-lookup"><span data-stu-id="23320-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="23320-137">在 [ **搜尋** ] 欄位中輸入 URL。</span><span class="sxs-lookup"><span data-stu-id="23320-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="23320-138">按一下搜尋圖示或按 **enter** 鍵。</span><span class="sxs-lookup"><span data-stu-id="23320-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="23320-139">顯示 URL 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="23320-139">Details about the URL are displayed.</span></span> <span data-ttu-id="23320-140">附注：只會針對來自組織中裝置的通訊所看到的 URLs 傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="23320-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="23320-141">使用搜尋篩選以定義搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="23320-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="23320-142">您也可以使用 [時程表] 搜尋方塊來篩選組織中所看到之所有裝置的顯示結果，與 URL 有關，與通訊和上次觀測的日期相關聯的檔。</span><span class="sxs-lookup"><span data-stu-id="23320-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="23320-143">按一下任一裝置名稱將會帶您前往該裝置的視圖，您可以在其中繼續調查報告的警示、行為和事件。</span><span class="sxs-lookup"><span data-stu-id="23320-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="23320-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="23320-144">Related topics</span></span>
- [<span data-ttu-id="23320-145">查看和組織 Microsoft Defender for Endpoint 警示佇列</span><span class="sxs-lookup"><span data-stu-id="23320-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="23320-146">管理 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="23320-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="23320-147">調查 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="23320-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="23320-148">調查與 Microsoft Defender for Endpoint alert 相關聯的檔案</span><span class="sxs-lookup"><span data-stu-id="23320-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="23320-149">調查 Microsoft Defender for Endpoint Devices 清單中的裝置</span><span class="sxs-lookup"><span data-stu-id="23320-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="23320-150">調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="23320-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="23320-151">調查 Microsoft Defender for Endpoint 中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="23320-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
