---
title: 查看和組織 Microsoft Defender for Endpoint devices 清單
description: 深入瞭解您可以從 [裝置] 清單中使用的功能，例如排序、篩選和匯出清單，以加強調查。
keywords: 排序、篩選、匯出、csv、裝置名稱、網域、最後一次查看的內部 IP、健康狀態、作用中警示、作用中的惡意程式碼偵測、威脅類別、審閱警示、網路、連線、惡意程式碼、一般惡意程式碼、stealer、勒索軟體、攻擊、威脅、一般惡意程式碼、不需要的軟體
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
ms.openlocfilehash: a031a35929f319e87a9ad1a9ca48d6bf95a3ef72
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861572"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="86d2d-104">查看和組織 Microsoft Defender for Endpoint Devices 清單</span><span class="sxs-lookup"><span data-stu-id="86d2d-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="86d2d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="86d2d-105">**Applies to:**</span></span>
- [<span data-ttu-id="86d2d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="86d2d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="86d2d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86d2d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="86d2d-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="86d2d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="86d2d-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="86d2d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="86d2d-110">[ **裝置] 清單** 會顯示您網路中產生警示的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="86d2d-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="86d2d-111">依預設，佇列會顯示過去30天內看到的裝置。</span><span class="sxs-lookup"><span data-stu-id="86d2d-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="86d2d-112">您將會看到諸如網域、風險層級、作業系統平臺及其他詳細資訊等資訊，以便更輕鬆地識別最具風險的裝置。</span><span class="sxs-lookup"><span data-stu-id="86d2d-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="86d2d-113">您可以選擇從多個選項自訂 [裝置] 清單視圖。</span><span class="sxs-lookup"><span data-stu-id="86d2d-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="86d2d-114">您可以在上方導覽上進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="86d2d-114">On the top navigation you can:</span></span>

- <span data-ttu-id="86d2d-115">新增或移除欄</span><span class="sxs-lookup"><span data-stu-id="86d2d-115">Add or remove columns</span></span>
- <span data-ttu-id="86d2d-116">以 CSV 格式匯出整個清單</span><span class="sxs-lookup"><span data-stu-id="86d2d-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="86d2d-117">選取每頁顯示的專案數</span><span class="sxs-lookup"><span data-stu-id="86d2d-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="86d2d-118">套用篩選</span><span class="sxs-lookup"><span data-stu-id="86d2d-118">Apply filters</span></span>

<span data-ttu-id="86d2d-119">在上架過程中， **裝置清單** 會隨著裝置開始報告感應器資料而逐漸填滿。</span><span class="sxs-lookup"><span data-stu-id="86d2d-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="86d2d-120">使用此視圖在線上時追蹤架端點，或下載完整的端點清單做為 CSV 檔案以供離線分析使用。</span><span class="sxs-lookup"><span data-stu-id="86d2d-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="86d2d-121">如果您匯出的是裝置清單，它會包含您組織中的每一部裝置。</span><span class="sxs-lookup"><span data-stu-id="86d2d-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="86d2d-122">視您的組織規模而定，可能需要很長的時間才能下載。</span><span class="sxs-lookup"><span data-stu-id="86d2d-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="86d2d-123">以 CSV 格式匯出清單會以未篩選的方式顯示資料。</span><span class="sxs-lookup"><span data-stu-id="86d2d-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="86d2d-124">CSV 檔案會包含組織中的所有裝置，不論該視圖本身所套用的篩選。</span><span class="sxs-lookup"><span data-stu-id="86d2d-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![具有裝置清單的裝置清單影像](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="86d2d-126">排序及篩選裝置清單</span><span class="sxs-lookup"><span data-stu-id="86d2d-126">Sort and filter the device list</span></span>

<span data-ttu-id="86d2d-127">您可以套用下列篩選器來限制警示清單，並取得更具焦點的視圖。</span><span class="sxs-lookup"><span data-stu-id="86d2d-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="86d2d-128">風險層級</span><span class="sxs-lookup"><span data-stu-id="86d2d-128">Risk level</span></span>

<span data-ttu-id="86d2d-129">風險層級會根據因素的組合，反映裝置的整體風險評估，包括裝置上作用中警示的類型和嚴重性。</span><span class="sxs-lookup"><span data-stu-id="86d2d-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="86d2d-130">解決作用中的警示、核准修復活動，以及抑制後續的警示，可降低風險等級。</span><span class="sxs-lookup"><span data-stu-id="86d2d-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="86d2d-131">公開層級</span><span class="sxs-lookup"><span data-stu-id="86d2d-131">Exposure level</span></span>

<span data-ttu-id="86d2d-132">暴露層級會根據未決安全性建議的累計影響，反映裝置目前的公開情況。</span><span class="sxs-lookup"><span data-stu-id="86d2d-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="86d2d-133">可能的層級為低、中和高。</span><span class="sxs-lookup"><span data-stu-id="86d2d-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="86d2d-134">危險性低表示您的裝置不易受到攻擊。</span><span class="sxs-lookup"><span data-stu-id="86d2d-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="86d2d-135">如果暴露層級說「沒有可用的資料」，這可能是因為這種情況的原因：</span><span class="sxs-lookup"><span data-stu-id="86d2d-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="86d2d-136">裝置停止報告超過30天–在此情況下，它會被視為非使用中，而且不會計算曝光</span><span class="sxs-lookup"><span data-stu-id="86d2d-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="86d2d-137">不支援裝置作業系統-請參閱 [Microsoft Defender For Endpoint 的基本需求](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="86d2d-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="86d2d-138">具有陳舊代理程式的裝置 (很少) </span><span class="sxs-lookup"><span data-stu-id="86d2d-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="86d2d-139">作業系統平臺</span><span class="sxs-lookup"><span data-stu-id="86d2d-139">OS Platform</span></span>

<span data-ttu-id="86d2d-140">僅選取您想要調查的作業系統平臺。</span><span class="sxs-lookup"><span data-stu-id="86d2d-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="86d2d-141">健康狀態</span><span class="sxs-lookup"><span data-stu-id="86d2d-141">Health state</span></span>

<span data-ttu-id="86d2d-142">依下列裝置健康狀態進行篩選：</span><span class="sxs-lookup"><span data-stu-id="86d2d-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="86d2d-143">使用 **中–對服務主動報告** 感應器資料的裝置。</span><span class="sxs-lookup"><span data-stu-id="86d2d-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="86d2d-144">**非** 使用中–已完全停止傳送信號的裝置超過7天。</span><span class="sxs-lookup"><span data-stu-id="86d2d-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="86d2d-145">未 **正確**–與服務通訊或無法傳送感應器資料的裝置。</span><span class="sxs-lookup"><span data-stu-id="86d2d-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="86d2d-146">設定錯誤的裝置可進一步分類為：</span><span class="sxs-lookup"><span data-stu-id="86d2d-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="86d2d-147">無感應器資料</span><span class="sxs-lookup"><span data-stu-id="86d2d-147">No sensor data</span></span>
  - <span data-ttu-id="86d2d-148">受損的通訊</span><span class="sxs-lookup"><span data-stu-id="86d2d-148">Impaired communications</span></span>

  <span data-ttu-id="86d2d-149">如需如何解決誤設定之裝置之問題的詳細資訊，請參閱， [修正狀況不良的感應器](fix-unhealthy-sensors.md)。</span><span class="sxs-lookup"><span data-stu-id="86d2d-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="86d2d-150">防病毒狀態</span><span class="sxs-lookup"><span data-stu-id="86d2d-150">Antivirus status</span></span>

<span data-ttu-id="86d2d-151">依防病毒狀態篩選裝置。</span><span class="sxs-lookup"><span data-stu-id="86d2d-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="86d2d-152">僅適用于使用中 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="86d2d-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="86d2d-153">**Disabled** -已關閉病毒 & 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="86d2d-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="86d2d-154">**不報告** -病毒 & 威脅防護不會報告。</span><span class="sxs-lookup"><span data-stu-id="86d2d-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="86d2d-155">**未更新** -病毒 & 威脅防護不是最新的。</span><span class="sxs-lookup"><span data-stu-id="86d2d-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="86d2d-156">如需詳細資訊，請參閱 [View The 威脅 & 弱點管理儀表板](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="86d2d-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="86d2d-157">威脅緩解狀態</span><span class="sxs-lookup"><span data-stu-id="86d2d-157">Threat mitigation status</span></span>

<span data-ttu-id="86d2d-158">若要查看可能受到特定威脅影響的裝置，請從下拉式功能表中選取威脅，然後選取需要緩解的弱點方位。</span><span class="sxs-lookup"><span data-stu-id="86d2d-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="86d2d-159">若要深入瞭解特定威脅，請參閱 [威脅分析](threat-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="86d2d-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="86d2d-160">如需緩解資訊，請參閱 [威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)。</span><span class="sxs-lookup"><span data-stu-id="86d2d-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="86d2d-161">Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="86d2d-161">Windows 10 version</span></span>

<span data-ttu-id="86d2d-162">僅選取您想要調查的 Windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="86d2d-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="86d2d-163">& 群組的標記</span><span class="sxs-lookup"><span data-stu-id="86d2d-163">Tags & Groups</span></span>

<span data-ttu-id="86d2d-164">根據您已新增至個別裝置的分組及標記，篩選清單。</span><span class="sxs-lookup"><span data-stu-id="86d2d-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="86d2d-165">請參閱 [建立及管理裝置標記](machine-tags.md) ，以及 [建立和管理裝置群組](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="86d2d-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="86d2d-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="86d2d-166">Related topics</span></span>

- [<span data-ttu-id="86d2d-167">調查 Microsoft Defender for Endpoint Devices 清單中的裝置</span><span class="sxs-lookup"><span data-stu-id="86d2d-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
