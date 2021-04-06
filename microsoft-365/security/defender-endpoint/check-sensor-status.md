---
title: 檢查 Microsoft Defender ATP 中感應器的健康狀態
description: 在裝置上檢查感應器的健全狀況，以找出未正確配置、非使用中或未報告感應器資料的情況。
keywords: 感應器、感應器健康情況、未設定的狀態、非使用中、無感應器資料、感應器資料、未削弱的通訊、通訊
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 21313463519383f4bf052465a0d907d2df293ec8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165270"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="51fbb-104">檢查 Microsoft Defender for Endpoint 中的感應器健康狀態</span><span class="sxs-lookup"><span data-stu-id="51fbb-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51fbb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="51fbb-105">**Applies to:**</span></span>
- [<span data-ttu-id="51fbb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="51fbb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51fbb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51fbb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="51fbb-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="51fbb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="51fbb-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="51fbb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="51fbb-110">在 [安全性作業] 儀表板上會找到 **具有感應器問題** 磚的裝置。</span><span class="sxs-lookup"><span data-stu-id="51fbb-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="51fbb-111">此麻將牌提供個別裝置提供感應器資料及與 Defender for Endpoint service 通訊之能力的資訊。</span><span class="sxs-lookup"><span data-stu-id="51fbb-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="51fbb-112">它會報告需要注意的裝置數量，並協助您找出有問題的裝置，並採取動作修正已知問題。</span><span class="sxs-lookup"><span data-stu-id="51fbb-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="51fbb-113">磚上有兩個狀態指示器，可提供無法正確報告給服務之裝置數目的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="51fbb-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="51fbb-114">設定 **錯誤**-這些裝置可能會部分向 Defender for Endpoint service 報告感應器資料，而且可能會發生需要修正的設定錯誤。</span><span class="sxs-lookup"><span data-stu-id="51fbb-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="51fbb-115">**非** 使用中-過去一個月內，已停止向 Defender for Endpoint service 報告的裝置超過7天。</span><span class="sxs-lookup"><span data-stu-id="51fbb-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="51fbb-116">按一下任一群組可將您導向至 [ **裝置] 清單**，並根據您的選擇加以篩選。</span><span class="sxs-lookup"><span data-stu-id="51fbb-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![具有感應器問題磚之裝置的螢幕擷取畫面](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="51fbb-118">在 [ **裝置] 清單** 上，您可以依下列狀態篩選健康狀態清單：</span><span class="sxs-lookup"><span data-stu-id="51fbb-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="51fbb-119">**主動-正在** 向 Defender for Endpoint service 報告的裝置。</span><span class="sxs-lookup"><span data-stu-id="51fbb-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="51fbb-120">設定 **錯誤**-這些裝置可能會部分向 Defender for Endpoint service 報告感應器資料，但有需要修正的設定錯誤。</span><span class="sxs-lookup"><span data-stu-id="51fbb-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="51fbb-121">誤設定的裝置可以有下列問題的其中一個或兩個組合：</span><span class="sxs-lookup"><span data-stu-id="51fbb-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="51fbb-122">**沒有感應器資料** -裝置已停止傳送感應器資料。</span><span class="sxs-lookup"><span data-stu-id="51fbb-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="51fbb-123">您可以從裝置觸發有限的警示。</span><span class="sxs-lookup"><span data-stu-id="51fbb-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="51fbb-124">受到影響的 **通訊**-與裝置通訊的功能遭到削弱。</span><span class="sxs-lookup"><span data-stu-id="51fbb-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="51fbb-125">傳送檔案以取得深入分析、封鎖檔案、從網路隔離裝置，以及其他需要與裝置通訊的動作都可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="51fbb-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="51fbb-126">**非** 使用中-已停止向 Defender for Endpoint service 報告的裝置。</span><span class="sxs-lookup"><span data-stu-id="51fbb-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="51fbb-127">您也可以使用 **匯出** 功能，以 CSV 格式下載整個清單。</span><span class="sxs-lookup"><span data-stu-id="51fbb-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="51fbb-128">如需篩選的詳細資訊，請參閱 [查看和組織裝置清單](machines-view-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="51fbb-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="51fbb-129">以 CSV 格式匯出清單以顯示未篩選的資料。</span><span class="sxs-lookup"><span data-stu-id="51fbb-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="51fbb-130">CSV 檔案會包含組織中的所有裝置，不論該視圖本身所套用的篩選為何，也視您的組織規模大小而定，下載時間很長。</span><span class="sxs-lookup"><span data-stu-id="51fbb-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![裝置清單頁面的螢幕擷取畫面](images/atp-devices-list-page.png)

<span data-ttu-id="51fbb-132">當您按一下設定不當或非使用的裝置時，您可以查看裝置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="51fbb-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="51fbb-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="51fbb-133">Related topic</span></span>
- [<span data-ttu-id="51fbb-134">修正用於端點的 Defender 中的狀況不良感應器</span><span class="sxs-lookup"><span data-stu-id="51fbb-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)