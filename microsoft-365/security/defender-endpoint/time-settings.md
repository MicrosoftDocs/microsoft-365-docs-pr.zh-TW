---
title: Microsoft Defender 安全中心時區設定
description: 使用這裡所包含的資訊來設定 Microsoft Defender 安全中心時區設定和查看授權資訊。
keywords: 設定，Microsoft Defender，cybersecurity 威脅情報，高級威脅防護，時區，utc，本機時間，授權
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
ms.openlocfilehash: c6338155aae3605ac5721958363b8c2d86618d9b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183846"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="c3613-104">Microsoft Defender 安全中心時區設定</span><span class="sxs-lookup"><span data-stu-id="c3613-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c3613-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c3613-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3613-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c3613-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3613-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3613-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)




><span data-ttu-id="c3613-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c3613-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c3613-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c3613-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="c3613-110">使用 **時區** 功能表時區 ![ 設定 icon1 ](images/atp-time-zone.png) 來設定時區及查看授權資訊。</span><span class="sxs-lookup"><span data-stu-id="c3613-110">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="c3613-111">時區設定</span><span class="sxs-lookup"><span data-stu-id="c3613-111">Time zone settings</span></span>
<span data-ttu-id="c3613-112">在感覺和實際 cyberattacks 的評估和分析中，時間方面很重要。</span><span class="sxs-lookup"><span data-stu-id="c3613-112">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="c3613-113">Cyberforensic 調查常常會依靠時間戳記將事件的順序組合在一起。</span><span class="sxs-lookup"><span data-stu-id="c3613-113">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="c3613-114">您的系統必須反映正確的時區設定。</span><span class="sxs-lookup"><span data-stu-id="c3613-114">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="c3613-115">Microsoft Defender for Endpoint 可顯示協調世界時 (UTC) 或本機時間。</span><span class="sxs-lookup"><span data-stu-id="c3613-115">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="c3613-116">您目前的時區設定會顯示在 [Microsoft Defender for Endpoint] 功能表中。</span><span class="sxs-lookup"><span data-stu-id="c3613-116">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="c3613-117">您可以在 [時區] 功能表中變更 **顯示時區。**</span><span class="sxs-lookup"><span data-stu-id="c3613-117">You can change the displayed time zone in the **Time zone** menu.</span></span>

![時區設定 icon2](images/atp-time-zone-menu.png)<span data-ttu-id="c3613-119">.</span><span class="sxs-lookup"><span data-stu-id="c3613-119">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="c3613-120">UTC 時區</span><span class="sxs-lookup"><span data-stu-id="c3613-120">UTC time zone</span></span>
<span data-ttu-id="c3613-121">Microsoft Defender for Endpoint 預設會使用 UTC 時間。</span><span class="sxs-lookup"><span data-stu-id="c3613-121">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="c3613-122">將 Microsoft Defender for Endpoint 時區設定為 UTC 時，會顯示所有使用者的所有系統時間戳記 (警示、事件及其他使用者) 。</span><span class="sxs-lookup"><span data-stu-id="c3613-122">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="c3613-123">這可協助在全球各地的不同位置運作的安全性分析師，在調查事件時使用相同的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="c3613-123">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="c3613-124">本機時區</span><span class="sxs-lookup"><span data-stu-id="c3613-124">Local time zone</span></span>
<span data-ttu-id="c3613-125">您可以選擇讓 Microsoft Defender for Endpoint 使用本機時區設定。</span><span class="sxs-lookup"><span data-stu-id="c3613-125">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="c3613-126">所有警示和事件都會以您的本機時區來顯示。</span><span class="sxs-lookup"><span data-stu-id="c3613-126">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="c3613-127">從您的裝置的區域設定中取得本機時區。</span><span class="sxs-lookup"><span data-stu-id="c3613-127">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="c3613-128">如果您變更區域設定，Microsoft Defender for Endpoint 時區也會變更。</span><span class="sxs-lookup"><span data-stu-id="c3613-128">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="c3613-129">選擇此設定表示顯示在 Microsoft Defender for Endpoint 中的時間戳記將會對齊所有 Microsoft Defender for Endpoint 使用者的本機時間。</span><span class="sxs-lookup"><span data-stu-id="c3613-129">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="c3613-130">位於不同全域位置的分析師現在會根據其區域設定，看到 Microsoft Defender for Endpoint 警示。</span><span class="sxs-lookup"><span data-stu-id="c3613-130">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="c3613-131">若分析員位於單一位置，選擇使用當地時間會非常有用。</span><span class="sxs-lookup"><span data-stu-id="c3613-131">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="c3613-132">在此情況下，使事件與本地時間（例如，當本機使用者按一下可疑的電子郵件連結時）可能會比較容易。</span><span class="sxs-lookup"><span data-stu-id="c3613-132">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="c3613-133">設定時區</span><span class="sxs-lookup"><span data-stu-id="c3613-133">Set the time zone</span></span>
<span data-ttu-id="c3613-134">Microsoft Defender for Endpoint 時區預設會設定為 UTC。</span><span class="sxs-lookup"><span data-stu-id="c3613-134">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="c3613-135">設定時區也會變更所有 Microsoft Defender for Endpoint views 的時間。</span><span class="sxs-lookup"><span data-stu-id="c3613-135">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="c3613-136">若要設定時區：</span><span class="sxs-lookup"><span data-stu-id="c3613-136">To set the time zone:</span></span>

1. <span data-ttu-id="c3613-137">按一下 [ **時區** ] 功能表的 [時區 ![ 設定 icon3] ](images/atp-time-zone.png) 。</span><span class="sxs-lookup"><span data-stu-id="c3613-137">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="c3613-138">選取 [ **時區 UTC** ] 標記。</span><span class="sxs-lookup"><span data-stu-id="c3613-138">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="c3613-139">選取 [ **時區 UTC** ] 或 [本機時區]，例如-7:00。</span><span class="sxs-lookup"><span data-stu-id="c3613-139">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="c3613-140">地區設定</span><span class="sxs-lookup"><span data-stu-id="c3613-140">Regional settings</span></span>
<span data-ttu-id="c3613-141">若要對 Microsoft Defender for Endpoint 套用不同的日期格式，請使用 Internet Explorer (IE) 和 Microsoft Edge (Edge) 的區域設定。</span><span class="sxs-lookup"><span data-stu-id="c3613-141">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="c3613-142">如果您使用的是其他瀏覽器（如 Google Chrome），請遵循必要的步驟來變更該瀏覽器的時間和日期設定。</span><span class="sxs-lookup"><span data-stu-id="c3613-142">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="c3613-143">**Internet Explorer (IE) 和 Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="c3613-143">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="c3613-144">IE 和 Microsoft Edge 使用 [控制台] 的 [**時鐘、語言及地區**] 選項中所設定的 **區域** 設定。</span><span class="sxs-lookup"><span data-stu-id="c3613-144">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="c3613-145">地區格式的已知問題</span><span class="sxs-lookup"><span data-stu-id="c3613-145">Known issues with regional formats</span></span>

<span data-ttu-id="c3613-146">**日期和時間格式**</span><span class="sxs-lookup"><span data-stu-id="c3613-146">**Date and time formats**</span></span><br>
<span data-ttu-id="c3613-147">時間和日期格式有一些已知的問題。</span><span class="sxs-lookup"><span data-stu-id="c3613-147">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="c3613-148">如果您將區域設定設定為支援的格式以外的任何值，則入口網站可能無法正確反映您的設定。</span><span class="sxs-lookup"><span data-stu-id="c3613-148">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="c3613-149">支援下列日期和時間格式：</span><span class="sxs-lookup"><span data-stu-id="c3613-149">The following date and time formats are supported:</span></span>
- <span data-ttu-id="c3613-150">日期格式 MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="c3613-150">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="c3613-151">日期格式 dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="c3613-151">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="c3613-152">時間格式 hh： mm： ss (12 小時格式) </span><span class="sxs-lookup"><span data-stu-id="c3613-152">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="c3613-153">目前不支援下列日期和時間格式：</span><span class="sxs-lookup"><span data-stu-id="c3613-153">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="c3613-154">日期格式 yyyy 月</span><span class="sxs-lookup"><span data-stu-id="c3613-154">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="c3613-155">日期格式 dd yy</span><span class="sxs-lookup"><span data-stu-id="c3613-155">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="c3613-156">日期格式 dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="c3613-156">Date format dd/MM/yy</span></span>
- <span data-ttu-id="c3613-157">日期格式 MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="c3613-157">Date format MM/dd/yy</span></span>
- <span data-ttu-id="c3613-158">日期格式（yy）。</span><span class="sxs-lookup"><span data-stu-id="c3613-158">Date format with yy.</span></span> <span data-ttu-id="c3613-159">只會顯示 yyyy。</span><span class="sxs-lookup"><span data-stu-id="c3613-159">Will only show yyyy.</span></span>
- <span data-ttu-id="c3613-160">時間格式 HH： mm： ss (24 小時格式) </span><span class="sxs-lookup"><span data-stu-id="c3613-160">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="c3613-161">**數位中使用的十進位符號**</span><span class="sxs-lookup"><span data-stu-id="c3613-161">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="c3613-162">使用的十進位符號永遠是一個點，即使已選取 [**區域** 設定] 中的 [**數位** 格式] 設定中的逗號也是一樣。</span><span class="sxs-lookup"><span data-stu-id="c3613-162">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="c3613-163">例如，15，「15.5 K」會顯示為 K。</span><span class="sxs-lookup"><span data-stu-id="c3613-163">For example, 15,5K is displayed as 15.5K.</span></span>


