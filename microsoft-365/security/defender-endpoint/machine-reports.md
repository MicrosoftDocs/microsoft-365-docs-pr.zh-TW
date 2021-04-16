---
title: Microsoft Defender for Endpoint 中的裝置健康情況和符合性報告
description: 使用裝置健康情況和合規性報告追蹤裝置健康狀態偵測、防病毒狀態、作業系統平臺及 Windows 10 版本
keywords: 健康狀態、防毒程式、作業系統平臺、windows 10 版本、版本、健康情況、規範、狀態
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
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860288"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="65013-104">Microsoft Defender for Endpoint 中的裝置健康情況和符合性報告</span><span class="sxs-lookup"><span data-stu-id="65013-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="65013-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="65013-105">**Applies to:**</span></span>
- [<span data-ttu-id="65013-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="65013-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65013-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65013-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="65013-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="65013-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="65013-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="65013-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="65013-110">裝置狀態報表提供組織中裝置的高層級資訊。</span><span class="sxs-lookup"><span data-stu-id="65013-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="65013-111">報告包含趨勢資訊，顯示感應器狀況狀態、防病毒狀態、作業系統平臺及 Windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="65013-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="65013-112">儀表板分為兩個區段： ![ 裝置報表的影像](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="65013-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="65013-113">區段</span><span class="sxs-lookup"><span data-stu-id="65013-113">Section</span></span> | <span data-ttu-id="65013-114">說明</span><span class="sxs-lookup"><span data-stu-id="65013-114">Description</span></span>
:---|:---
<span data-ttu-id="65013-115">1</span><span class="sxs-lookup"><span data-stu-id="65013-115">1</span></span> | <span data-ttu-id="65013-116">裝置趨勢</span><span class="sxs-lookup"><span data-stu-id="65013-116">Device trends</span></span>
<span data-ttu-id="65013-117">第</span><span class="sxs-lookup"><span data-stu-id="65013-117">2</span></span> | <span data-ttu-id="65013-118">目前日期 (裝置摘要) </span><span class="sxs-lookup"><span data-stu-id="65013-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="65013-119">裝置趨勢</span><span class="sxs-lookup"><span data-stu-id="65013-119">Device trends</span></span> 
<span data-ttu-id="65013-120">依預設，裝置趨勢會顯示30天期間的裝置資訊，從最近的全天結束。</span><span class="sxs-lookup"><span data-stu-id="65013-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="65013-121">若要深入瞭解組織中發生的趨勢，您可以調整顯示的時段，以微調報告期間。</span><span class="sxs-lookup"><span data-stu-id="65013-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="65013-122">若要調整時段，請從下拉式選項中選取時間範圍：</span><span class="sxs-lookup"><span data-stu-id="65013-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="65013-123">30 天</span><span class="sxs-lookup"><span data-stu-id="65013-123">30 days</span></span>
- <span data-ttu-id="65013-124">3 個月</span><span class="sxs-lookup"><span data-stu-id="65013-124">3 months</span></span>
- <span data-ttu-id="65013-125">6 個月</span><span class="sxs-lookup"><span data-stu-id="65013-125">6 months</span></span>
- <span data-ttu-id="65013-126">自訂</span><span class="sxs-lookup"><span data-stu-id="65013-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="65013-127">這些篩選器僅適用于 [裝置趨勢] 區段。</span><span class="sxs-lookup"><span data-stu-id="65013-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="65013-128">它不會影響裝置摘要區段。</span><span class="sxs-lookup"><span data-stu-id="65013-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="65013-129">裝置摘要</span><span class="sxs-lookup"><span data-stu-id="65013-129">Device summary</span></span> 
<span data-ttu-id="65013-130">在裝置趨勢顯示趨勢裝置資訊時，裝置摘要會顯示裝置資訊的範圍是目前的日期。</span><span class="sxs-lookup"><span data-stu-id="65013-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="65013-131">在 [摘要] 區段中反映的資料範圍是在目前日期之前的180天。</span><span class="sxs-lookup"><span data-stu-id="65013-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="65013-132">例如，如果今天的日期是2019年3月27日，則 [摘要] 區段中的資料會反映從9月28日開始，2018到3月 2019 27 日的數位。</span><span class="sxs-lookup"><span data-stu-id="65013-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="65013-133">在 [趨勢] 區段上套用的篩選不會在 [摘要] 區段上套用。</span><span class="sxs-lookup"><span data-stu-id="65013-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="65013-134">[裝置趨勢] 區段可讓您向下流覽至已套用對應篩選的 [裝置] 清單。</span><span class="sxs-lookup"><span data-stu-id="65013-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="65013-135">例如，按一下感應器健康狀態卡片上的非作用中的條碼，會顯示 [裝置] 清單，其中的結果只會顯示其感應器狀態為「非使用中」的裝置。</span><span class="sxs-lookup"><span data-stu-id="65013-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="65013-136">裝置屬性</span><span class="sxs-lookup"><span data-stu-id="65013-136">Device attributes</span></span>
<span data-ttu-id="65013-137">報告是由顯示下列裝置屬性的卡片所組成：</span><span class="sxs-lookup"><span data-stu-id="65013-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="65013-138">**健康狀態**：顯示裝置上感應器狀態的相關資訊，提供作用中裝置的匯總視圖、未使用的通訊、非使用中或未看到的感應器資料。</span><span class="sxs-lookup"><span data-stu-id="65013-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="65013-139">**Active Windows 10 裝置的防毒程式狀態**：顯示裝置數目及 Microsoft Defender 防病毒的狀態。</span><span class="sxs-lookup"><span data-stu-id="65013-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="65013-140">**作業系統平臺**：顯示組織記憶體在的作業系統平臺散佈。</span><span class="sxs-lookup"><span data-stu-id="65013-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="65013-141">**Windows 10 版本**：顯示組織中 windows 10 裝置和其版本的散佈。</span><span class="sxs-lookup"><span data-stu-id="65013-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="65013-142">篩選資料</span><span class="sxs-lookup"><span data-stu-id="65013-142">Filter data</span></span>
 
<span data-ttu-id="65013-143">使用提供的篩選，以包含或排除具有特定屬性的裝置。</span><span class="sxs-lookup"><span data-stu-id="65013-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="65013-144">您可以從裝置屬性選取多個要套用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="65013-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="65013-145">這些篩選器適用于報告中的 **所有** 卡片。</span><span class="sxs-lookup"><span data-stu-id="65013-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="65013-146">例如，若要顯示具有使用中感應器健全狀態的 Windows 10 裝置相關資料：</span><span class="sxs-lookup"><span data-stu-id="65013-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="65013-147">在 [篩選] 底下 **> 感應器健全狀況狀態 > Active**。</span><span class="sxs-lookup"><span data-stu-id="65013-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="65013-148">然後，選取 [ **作業系統平臺] > Windows 10**。</span><span class="sxs-lookup"><span data-stu-id="65013-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="65013-149">選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="65013-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="65013-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="65013-150">Related topic</span></span>
- [<span data-ttu-id="65013-151">威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="65013-151">Threat protection report</span></span>](threat-protection-reports.md)
