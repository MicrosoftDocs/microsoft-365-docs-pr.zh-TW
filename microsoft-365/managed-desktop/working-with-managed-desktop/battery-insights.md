---
title: 電池深入解析
description: 顯示有關預測電池壽命和最上層電量消費者的資料的報告
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579707"
---
# <a name="battery-insights"></a><span data-ttu-id="30768-104">電池深入解析</span><span class="sxs-lookup"><span data-stu-id="30768-104">Battery insights</span></span>
<span data-ttu-id="30768-105">此視圖會為 Microsoft 受管理的桌面裝置提供電源、電池和應用程式使用方式度量。</span><span class="sxs-lookup"><span data-stu-id="30768-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="30768-106">在這些情況下，如果應用程式正在執行中且處於焦點，便會被視為「使用中」。</span><span class="sxs-lookup"><span data-stu-id="30768-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="30768-107">若要查看使用狀況資料，請選取 [ **電池** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="30768-107">To view usage data, select the **Battery** tab.</span></span>

![[電池] 窗格：左上方的每個裝置模型的預測電池壽命：左上方 (依應用程式) 右下方（深入）。](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="30768-110">預測電池壽命</span><span class="sxs-lookup"><span data-stu-id="30768-110">Predicted battery life</span></span>

<span data-ttu-id="30768-111">在 [ **預計電池壽命** ] 區域中，我們會針對您的裝置，依裝置模型所組織，提供預期電池壽命的預測。</span><span class="sxs-lookup"><span data-stu-id="30768-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="30768-112">這項資料衍生自您從 Microsoft 管理的桌面部署（也是報告資料）的隨機 <em>選擇</em> 裝置中的能源使用量、使用時間和電池容量。</span><span class="sxs-lookup"><span data-stu-id="30768-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="30768-113">此表格提供預測電池壽命 (以小時為單位）) 、其他 Microsoft 受管理桌面部署中相同模型的平均電池壽命，以及在您的環境中報告此資料的裝置數量。</span><span class="sxs-lookup"><span data-stu-id="30768-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="30768-114">選取欄標題以排序資料。</span><span class="sxs-lookup"><span data-stu-id="30768-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="30768-115">主要能源消費者</span><span class="sxs-lookup"><span data-stu-id="30768-115">Top energy consumers</span></span>

<span data-ttu-id="30768-116">在 [ **最熱門的能源消費者** ] 區域中，您將會發現環境中的應用程式，在 milliWatt) 中消耗最高的能耗 (mWh。</span><span class="sxs-lookup"><span data-stu-id="30768-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="30768-117">顯示的應用程式為每個特定裝置，您可以在左側的 **預測電池壽命** 區段中選取。</span><span class="sxs-lookup"><span data-stu-id="30768-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="30768-118">例如，若要查看 Microsoft Surface Book 2 裝置的每個應用程式消耗量，請選取 [電池壽命] 區域中的那一列。</span><span class="sxs-lookup"><span data-stu-id="30768-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="30768-119">如果您未選取任何模型，則所顯示的應用程式消耗資料是針對我們所有具有共同資料的應用程式。</span><span class="sxs-lookup"><span data-stu-id="30768-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="30768-120">在每個應用程式中，彩色區段會顯示應用程式在下列類別中所使用的能源使用方式：</span><span class="sxs-lookup"><span data-stu-id="30768-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="30768-121">CPU</span><span class="sxs-lookup"><span data-stu-id="30768-121">CPU</span></span>
- <span data-ttu-id="30768-122">顯示器</span><span class="sxs-lookup"><span data-stu-id="30768-122">Display</span></span>
- <span data-ttu-id="30768-123">網路</span><span class="sxs-lookup"><span data-stu-id="30768-123">Network</span></span>
- <span data-ttu-id="30768-124">其他</span><span class="sxs-lookup"><span data-stu-id="30768-124">Other</span></span>

<span data-ttu-id="30768-125">"Other" 可以包含各種來源的能量消耗，例如磁片活動、行動寬頻使用量和對內部阻力的能量遺失。</span><span class="sxs-lookup"><span data-stu-id="30768-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="30768-126">您可以使用右上角的功能表篩選此視圖，只顯示前景應用程式、背景應用程式或兩者。</span><span class="sxs-lookup"><span data-stu-id="30768-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="30768-127">前臺應用程式是指在過去28天內，已有使用者互動的應用程式，例如使用滑鼠選取某些專案。</span><span class="sxs-lookup"><span data-stu-id="30768-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="30768-128">深入解析</span><span class="sxs-lookup"><span data-stu-id="30768-128">Insights</span></span>

<span data-ttu-id="30768-129">**Insights** 區域會顯示 CPU 和網路類別中的前三個能源消費者。</span><span class="sxs-lookup"><span data-stu-id="30768-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="30768-130">與所有 Microsoft 受管理的桌面部署相比，這些專案消耗的能耗高於平均能耗。</span><span class="sxs-lookup"><span data-stu-id="30768-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="30768-131">由於大量取決於裝置使用時間和螢幕亮度設定，因此不會顯示顯示資源。</span><span class="sxs-lookup"><span data-stu-id="30768-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="30768-132">選取 [ **詳細資料** ] 欄中的清單以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="30768-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="30768-133">電池優化</span><span class="sxs-lookup"><span data-stu-id="30768-133">Battery optimization</span></span>

<span data-ttu-id="30768-134">Windows 10 提供許多 [裝置設定](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) ，以改善電源使用狀況，並增加 Microsoft 受管理桌面裝置的電池壽命。</span><span class="sxs-lookup"><span data-stu-id="30768-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="30768-135">其中的部分設定可能會減少其他 Windows 功能，因此您也必須考慮其他因素，例如組織中裝置的角色。</span><span class="sxs-lookup"><span data-stu-id="30768-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="30768-136">Windows 支援會維護這些 [電池儲存提示](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)的清單。</span><span class="sxs-lookup"><span data-stu-id="30768-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="30768-137">使用者可以自行調整某些設定，而不需要系統管理員提升或支援。</span><span class="sxs-lookup"><span data-stu-id="30768-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="30768-138">其他設定需要您組織的 IT 管理員提供支援。</span><span class="sxs-lookup"><span data-stu-id="30768-138">Other settings require support from your organization's IT administrator.</span></span>
