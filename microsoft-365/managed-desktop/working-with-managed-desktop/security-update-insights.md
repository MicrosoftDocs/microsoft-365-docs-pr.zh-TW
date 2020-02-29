---
title: Windows 安全性更新深入解析
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341263"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="ff3c2-103">Windows 安全性更新深入解析</span><span class="sxs-lookup"><span data-stu-id="ff3c2-103">Windows security update insights</span></span>
<span data-ttu-id="ff3c2-104">此檢視提供您的 Microsoft 受管理的電腦裝置概觀安全性更新的狀態。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="ff3c2-105">若要檢視流量資料，請選取 [ <strong>Windows 安全性更新</strong>] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows 安全性更新窗格： 長條圖的裝置狀態及更新版本，在左邊的欄中，更新經過一段時間在中心] 欄中和百分比的作用中裝置的部署] 群組中，部署進度以及採取到達 95%部署的天數在右邊欄位中的目標。](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="ff3c2-107">裝置狀態</span><span class="sxs-lookup"><span data-stu-id="ff3c2-107">Device status</span></span>

<span data-ttu-id="ff3c2-108">裝置更新的 Windows 更新，它們必須連線至網際網路，不休眠至少六個小時，其中兩個必須是連續範圍。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="ff3c2-109">只要裝置已連線且未休眠，它已被視為 」 中使用。 」</span><span class="sxs-lookup"><span data-stu-id="ff3c2-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="ff3c2-110">雖然很可能不符合這些需求的裝置將會更新，滿足它們的裝置必須要更新的最高的可能性。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="ff3c2-111">我們分類與這些字詞的 Windows 更新的內容中的裝置活動：</span><span class="sxs-lookup"><span data-stu-id="ff3c2-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="ff3c2-112"><strong>作用中：</strong>您必須符合最新的安全性更新版本的最低流量準則 （六個小時，兩個連續） 和簽入 Microsoft Intune 至少每隔五天的裝置</span><span class="sxs-lookup"><span data-stu-id="ff3c2-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="ff3c2-113"><strong>同步處理：</strong>最後一個 28 天內簽入 Intune 裝置</span><span class="sxs-lookup"><span data-stu-id="ff3c2-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="ff3c2-114"><strong>同步：</strong>裝置已<i>不</i>使用 Intune 簽入 28 天內</span><span class="sxs-lookup"><span data-stu-id="ff3c2-114"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="ff3c2-115">更新的版本狀態</span><span class="sxs-lookup"><span data-stu-id="ff3c2-115">Update version status</span></span>

<span data-ttu-id="ff3c2-116">Microsoft 發行月份中的每個第二個星期二的安全性更新。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="ff3c2-117">每個版本會新增已知的安全性弱點的重要更新。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="ff3c2-118">Microsoft 受管理的電腦可確保 95%的受管理的裝置會以最新可用的安全性更新每月更新。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="ff3c2-119">在其他時候緊急地址新威脅有時發行安全性更新。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="ff3c2-120">Microsoft 受管理電腦部署方式都很類似這些更新。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="ff3c2-121">我們分類與這些字詞的安全性更新版本的狀態：</span><span class="sxs-lookup"><span data-stu-id="ff3c2-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="ff3c2-122"><strong>目前：</strong>正在執行中的目前月份發行的更新的裝置</span><span class="sxs-lookup"><span data-stu-id="ff3c2-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="ff3c2-123"><strong>先前：</strong>執行於上個月發行更新的裝置</span><span class="sxs-lookup"><span data-stu-id="ff3c2-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="ff3c2-124"><strong>舊：</strong>執行前一個月之前發行任何安全性更新的裝置</span><span class="sxs-lookup"><span data-stu-id="ff3c2-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="ff3c2-125">您應該會看到一些裝置的<strong>較舊</strong>類別中-大型或可能得母體指出，因此我們可以調查，您應該報告至 Microsoft 受管理電腦的系統問題。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="ff3c2-126">部署進度</span><span class="sxs-lookup"><span data-stu-id="ff3c2-126">Deployment progress</span></span>

<span data-ttu-id="ff3c2-127">起點處的每個安全性更新發行週期，Microsoft 受管理的電腦會採用裝置母群體的快照集，並在 95%的該母體設定它的部署目標。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="ff3c2-128"><strong>部署進度</strong>區域顯示的歷史趨勢，更新每日、 追蹤更新部署符合此目標，針對每個版本的程度。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="ff3c2-129">此圖只會顯示作用中狀態的裝置。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="ff3c2-130">您可以使用下拉式清單功能表右上角，先前的更新週期檢視此資料。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="ff3c2-131">您在此功能表中選取的期間套用於所有的整個頁面上的資訊。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="ff3c2-132"><strong>已更新使用中的裝置部署群組</strong>] 區域中所示的進度更新安裝 Microsoft 受管理電腦部署群組的每個提供不同的檢視。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="ff3c2-133"><strong>天的時間可以達到目標</strong>區域會顯示所需的時間 95%的裝置總數以更新目前的安全性更新。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="ff3c2-134">雖然部署正在進行中，此區域會顯示<strong>仍更新</strong>直到 95%目標到達所選更新。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="ff3c2-135">裝置詳細資料] 區域</span><span class="sxs-lookup"><span data-stu-id="ff3c2-135">Device details area</span></span>

<span data-ttu-id="ff3c2-136">儀表板底部是表格顯示您的裝置，包括[裝置狀態](#device-status)和[更新版本狀態](#update-version-status)的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="ff3c2-137">您可以搜尋這份清單或篩選所列出的任何值。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-137">You can search this list or filter it by any listed value.</span></span>


![顯示的裝置名稱、 指派的使用者、 裝置狀態、 更新版本、 作業系統版本，以及日期欄上次同步處理之裝置的裝置詳細資料表格。](../../media/security-update-insights-device-table-sterile.png)
