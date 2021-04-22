---
title: Microsoft Defender 安全中心時區設定
description: 使用這裡所包含的資訊來設定 Microsoft Defender 安全中心時區設定和查看授權資訊。
keywords: 設定，Microsoft Defender，cybersecurity 威脅情報，Microsoft Defender for Endpoint，時區，utc，本機時間，授權
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: df55a1b0e92c24b5f52032330ef95bf19aeb8cb3
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932628"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="649b7-104">Microsoft Defender 安全中心時區設定</span><span class="sxs-lookup"><span data-stu-id="649b7-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="649b7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="649b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="649b7-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="649b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="649b7-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="649b7-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="649b7-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="649b7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="649b7-109">使用 **時區** 功能表時區 ![ 設定 icon1 ](images/atp-time-zone.png) 來設定時區及查看授權資訊。</span><span class="sxs-lookup"><span data-stu-id="649b7-109">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="649b7-110">時區設定</span><span class="sxs-lookup"><span data-stu-id="649b7-110">Time zone settings</span></span>
<span data-ttu-id="649b7-111">在感覺和實際 cyberattacks 的評估和分析中，時間方面很重要。</span><span class="sxs-lookup"><span data-stu-id="649b7-111">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="649b7-112">Cyberforensic 調查常常會依靠時間戳記將事件的順序組合在一起。</span><span class="sxs-lookup"><span data-stu-id="649b7-112">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="649b7-113">您的系統必須反映正確的時區設定。</span><span class="sxs-lookup"><span data-stu-id="649b7-113">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="649b7-114">Microsoft Defender for Endpoint 可顯示協調世界時 (UTC) 或本機時間。</span><span class="sxs-lookup"><span data-stu-id="649b7-114">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="649b7-115">您目前的時區設定會顯示在 [Microsoft Defender for Endpoint] 功能表中。</span><span class="sxs-lookup"><span data-stu-id="649b7-115">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="649b7-116">您可以在 [時區] 功能表中變更 **顯示時區。**</span><span class="sxs-lookup"><span data-stu-id="649b7-116">You can change the displayed time zone in the **Time zone** menu.</span></span>

![時區設定 icon2](images/atp-time-zone-menu.png)<span data-ttu-id="649b7-118">.</span><span class="sxs-lookup"><span data-stu-id="649b7-118">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="649b7-119">UTC 時區</span><span class="sxs-lookup"><span data-stu-id="649b7-119">UTC time zone</span></span>
<span data-ttu-id="649b7-120">Microsoft Defender for Endpoint 預設會使用 UTC 時間。</span><span class="sxs-lookup"><span data-stu-id="649b7-120">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="649b7-121">將 Microsoft Defender for Endpoint 時區設定為 UTC 時，會顯示所有使用者的所有系統時間戳記 (警示、事件及其他使用者) 。</span><span class="sxs-lookup"><span data-stu-id="649b7-121">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="649b7-122">這可協助在全球各地的不同位置運作的安全性分析師，在調查事件時使用相同的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="649b7-122">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="649b7-123">本機時區</span><span class="sxs-lookup"><span data-stu-id="649b7-123">Local time zone</span></span>
<span data-ttu-id="649b7-124">您可以選擇讓 Microsoft Defender for Endpoint 使用本機時區設定。</span><span class="sxs-lookup"><span data-stu-id="649b7-124">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="649b7-125">所有警示和事件都會以您的本機時區來顯示。</span><span class="sxs-lookup"><span data-stu-id="649b7-125">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="649b7-126">從您的裝置的區域設定中取得本機時區。</span><span class="sxs-lookup"><span data-stu-id="649b7-126">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="649b7-127">如果您變更區域設定，Microsoft Defender for Endpoint 時區也會變更。</span><span class="sxs-lookup"><span data-stu-id="649b7-127">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="649b7-128">選擇此設定表示顯示在 Microsoft Defender for Endpoint 中的時間戳記將會對齊所有 Microsoft Defender for Endpoint 使用者的本機時間。</span><span class="sxs-lookup"><span data-stu-id="649b7-128">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="649b7-129">位於不同全域位置的分析師現在會根據其區域設定，看到 Microsoft Defender for Endpoint 警示。</span><span class="sxs-lookup"><span data-stu-id="649b7-129">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="649b7-130">若分析員位於單一位置，選擇使用當地時間會非常有用。</span><span class="sxs-lookup"><span data-stu-id="649b7-130">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="649b7-131">在此情況下，使事件與本地時間（例如，當本機使用者按一下可疑的電子郵件連結時）可能會比較容易。</span><span class="sxs-lookup"><span data-stu-id="649b7-131">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="649b7-132">設定時區</span><span class="sxs-lookup"><span data-stu-id="649b7-132">Set the time zone</span></span>
<span data-ttu-id="649b7-133">Microsoft Defender for Endpoint 時區預設會設定為 UTC。</span><span class="sxs-lookup"><span data-stu-id="649b7-133">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="649b7-134">設定時區也會變更所有 Microsoft Defender for Endpoint views 的時間。</span><span class="sxs-lookup"><span data-stu-id="649b7-134">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="649b7-135">若要設定時區：</span><span class="sxs-lookup"><span data-stu-id="649b7-135">To set the time zone:</span></span>

1. <span data-ttu-id="649b7-136">按一下 [ **時區** ] 功能表的 [時區 ![ 設定 icon3] ](images/atp-time-zone.png) 。</span><span class="sxs-lookup"><span data-stu-id="649b7-136">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="649b7-137">選取 [ **時區 UTC** ] 標記。</span><span class="sxs-lookup"><span data-stu-id="649b7-137">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="649b7-138">選取 [ **時區 UTC** ] 或 [本機時區]，例如-7:00。</span><span class="sxs-lookup"><span data-stu-id="649b7-138">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="649b7-139">地區設定</span><span class="sxs-lookup"><span data-stu-id="649b7-139">Regional settings</span></span>
<span data-ttu-id="649b7-140">若要對 Microsoft Defender for Endpoint 套用不同的日期格式，請使用 Internet Explorer (IE) 和 Microsoft Edge (Edge) 的區域設定。</span><span class="sxs-lookup"><span data-stu-id="649b7-140">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="649b7-141">如果您使用的是其他瀏覽器（如 Google Chrome），請遵循必要的步驟來變更該瀏覽器的時間和日期設定。</span><span class="sxs-lookup"><span data-stu-id="649b7-141">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="649b7-142">**Internet Explorer (IE) 和 Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="649b7-142">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="649b7-143">IE 和 Microsoft Edge 使用 [控制台] 的 [**時鐘、語言及地區**] 選項中所設定的 **區域** 設定。</span><span class="sxs-lookup"><span data-stu-id="649b7-143">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="649b7-144">地區格式的已知問題</span><span class="sxs-lookup"><span data-stu-id="649b7-144">Known issues with regional formats</span></span>

<span data-ttu-id="649b7-145">**日期和時間格式**</span><span class="sxs-lookup"><span data-stu-id="649b7-145">**Date and time formats**</span></span><br>
<span data-ttu-id="649b7-146">時間和日期格式有一些已知的問題。</span><span class="sxs-lookup"><span data-stu-id="649b7-146">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="649b7-147">如果您將區域設定設定為支援的格式以外的任何值，則入口網站可能無法正確反映您的設定。</span><span class="sxs-lookup"><span data-stu-id="649b7-147">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="649b7-148">支援下列日期和時間格式：</span><span class="sxs-lookup"><span data-stu-id="649b7-148">The following date and time formats are supported:</span></span>
- <span data-ttu-id="649b7-149">日期格式 MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="649b7-149">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="649b7-150">日期格式 dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="649b7-150">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="649b7-151">時間格式 hh： mm： ss (12 小時格式) </span><span class="sxs-lookup"><span data-stu-id="649b7-151">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="649b7-152">目前不支援下列日期和時間格式：</span><span class="sxs-lookup"><span data-stu-id="649b7-152">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="649b7-153">日期格式 yyyy 月</span><span class="sxs-lookup"><span data-stu-id="649b7-153">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="649b7-154">日期格式 dd yy</span><span class="sxs-lookup"><span data-stu-id="649b7-154">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="649b7-155">日期格式 dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="649b7-155">Date format dd/MM/yy</span></span>
- <span data-ttu-id="649b7-156">日期格式 MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="649b7-156">Date format MM/dd/yy</span></span>
- <span data-ttu-id="649b7-157">日期格式（yy）。</span><span class="sxs-lookup"><span data-stu-id="649b7-157">Date format with yy.</span></span> <span data-ttu-id="649b7-158">只會顯示 yyyy。</span><span class="sxs-lookup"><span data-stu-id="649b7-158">Will only show yyyy.</span></span>
- <span data-ttu-id="649b7-159">時間格式 HH： mm： ss (24 小時格式) </span><span class="sxs-lookup"><span data-stu-id="649b7-159">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="649b7-160">**數位中使用的十進位符號**</span><span class="sxs-lookup"><span data-stu-id="649b7-160">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="649b7-161">使用的十進位符號永遠是一個點，即使已選取 [**區域** 設定] 中的 [**數位** 格式] 設定中的逗號也是一樣。</span><span class="sxs-lookup"><span data-stu-id="649b7-161">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="649b7-162">例如，15，「15.5 K」會顯示為 K。</span><span class="sxs-lookup"><span data-stu-id="649b7-162">For example, 15,5K is displayed as 15.5K.</span></span>


