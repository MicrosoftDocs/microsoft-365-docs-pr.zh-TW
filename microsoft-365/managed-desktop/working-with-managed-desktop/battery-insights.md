---
title: 電池深入解析
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 81b7a7c3db69d1c20f9a9cd8c6ea4a37b481ce59
ms.sourcegitcommit: 9b390881fe661deb0568b4b86a5a9094f3c795f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269384"
---
# <a name="battery-insights"></a><span data-ttu-id="3fe60-103">電池深入解析</span><span class="sxs-lookup"><span data-stu-id="3fe60-103">Battery insights</span></span>
<span data-ttu-id="3fe60-104">此檢視提供您的 Microsoft 受管理的電腦裝置電源、 電和應用程式使用狀況計量。</span><span class="sxs-lookup"><span data-stu-id="3fe60-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="3fe60-105">進行這些工作，應用程式被視為 「 使用 」 中，如果它正在執行，並在焦點。</span><span class="sxs-lookup"><span data-stu-id="3fe60-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="3fe60-106">若要檢視流量資料，請選取 [**電池**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3fe60-106">To view usage data, select the **Battery** tab.</span></span>

![電池窗格： 跨底部預測電池壽命，每個裝置模型在左上方] （依應用程式） 的上方能源消費者，在右上] 觀點資料表。](images/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="3fe60-109">預測的電池壽命</span><span class="sxs-lookup"><span data-stu-id="3fe60-109">Predicted battery life</span></span>

<span data-ttu-id="3fe60-110">在**Predicted 電池壽命**] 區域中，我們會提供您的裝置，依裝置型號的預期的電池壽命預測。</span><span class="sxs-lookup"><span data-stu-id="3fe60-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="3fe60-111">此資料被衍生自取樣能源使用量、 使用量的時間及從隨機<em>選取範圍</em>內的裝置 Microsoft 受管理電腦部署也會報告資料的電池容量。</span><span class="sxs-lookup"><span data-stu-id="3fe60-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="3fe60-112">表提供預測的電池壽命 （以小時為單位），平均電池壽命的相同模型其他 Microsoft 受管理電腦的部署，並報告您環境中的此資料的裝置數目。</span><span class="sxs-lookup"><span data-stu-id="3fe60-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="3fe60-113">藉由選取欄標題來排序資料。</span><span class="sxs-lookup"><span data-stu-id="3fe60-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="3fe60-114">上方能源消費者</span><span class="sxs-lookup"><span data-stu-id="3fe60-114">Top energy consumers</span></span>

<span data-ttu-id="3fe60-115">在**上方能源消費者**] 區域中，您會發現應用程式耗用 milliWatt 小時 (mWh) 中的大部分能源您環境中。</span><span class="sxs-lookup"><span data-stu-id="3fe60-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="3fe60-116">顯示應用程式是每個特定裝置，向左**Predicted 電池壽命**區段中選取。</span><span class="sxs-lookup"><span data-stu-id="3fe60-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="3fe60-117">例如，若要查看您 Microsft Surface Book 2 的裝置的每個應用程式使用率，請電池壽命區域中選取該資料列。</span><span class="sxs-lookup"><span data-stu-id="3fe60-117">For example, to see the per-app consumption for your Microsft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="3fe60-118">如果您未選取任何模型，所顯示的應用程式耗用資料是我們統稱有資料的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="3fe60-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="3fe60-119">每個應用程式，彩色的區段顯示您的應用程式的能源使用這些類別之間通訊：</span><span class="sxs-lookup"><span data-stu-id="3fe60-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="3fe60-120">CPU</span><span class="sxs-lookup"><span data-stu-id="3fe60-120">CPU</span></span>
- <span data-ttu-id="3fe60-121">顯示</span><span class="sxs-lookup"><span data-stu-id="3fe60-121">Display</span></span>
- <span data-ttu-id="3fe60-122">網路</span><span class="sxs-lookup"><span data-stu-id="3fe60-122">Network</span></span>
- <span data-ttu-id="3fe60-123">其他</span><span class="sxs-lookup"><span data-stu-id="3fe60-123">Other</span></span>

<span data-ttu-id="3fe60-124">「 其他 」 可能包含能源所消耗的各種來源，例如磁碟活動、 行動寬頻使用量和能源至內部的抗拒遺失。</span><span class="sxs-lookup"><span data-stu-id="3fe60-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="3fe60-125">您可以篩選此檢視，以顯示只有前景應用程式、 背景應用程式]，或兩者皆使用功能表右上角。</span><span class="sxs-lookup"><span data-stu-id="3fe60-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="3fe60-126">前景應用程式 」 是指有鎖 28 天內，例如選取某個項目與滑鼠與使用者互動。</span><span class="sxs-lookup"><span data-stu-id="3fe60-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="3fe60-127">深入資訊</span><span class="sxs-lookup"><span data-stu-id="3fe60-127">Insights</span></span>

<span data-ttu-id="3fe60-128">**深入了解**區域顯示上方的三個能源消費者 CPU 及網路類別。</span><span class="sxs-lookup"><span data-stu-id="3fe60-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="3fe60-129">這些項目會耗用高於平均能源相較於所有 Microsoft 受管理電腦部署。</span><span class="sxs-lookup"><span data-stu-id="3fe60-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="3fe60-130">我們不顯示顯示資源，因為它，取決於裝置使用量的時間和螢幕亮度設定。</span><span class="sxs-lookup"><span data-stu-id="3fe60-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="3fe60-131">如需詳細資訊的**詳細資料**] 欄中，請選取 [清單]。</span><span class="sxs-lookup"><span data-stu-id="3fe60-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="3fe60-132">電池最佳化</span><span class="sxs-lookup"><span data-stu-id="3fe60-132">Battery optimization</span></span>

<span data-ttu-id="3fe60-133">Windows 10 可提供許多[裝置設定](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)] 若要改善 power 使用量增加您的 Microsoft 受管理的電腦裝置的電池壽命。</span><span class="sxs-lookup"><span data-stu-id="3fe60-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="3fe60-134">其中一些設定可以降低其他 Windows 功能，所以您也必須考慮其他因素影響，例如您組織中裝置的角色。</span><span class="sxs-lookup"><span data-stu-id="3fe60-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="3fe60-135">Windows 支援維護[電池省電祕](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)這些的清單。</span><span class="sxs-lookup"><span data-stu-id="3fe60-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="3fe60-136">使用者可以調整自己而不需要系統管理員權限提高或支援某些設定。</span><span class="sxs-lookup"><span data-stu-id="3fe60-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="3fe60-137">其他設定需要支援您的組織從 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="3fe60-137">Other settings require support from your organization's IT administrator.</span></span>
