---
title: 評估 Microsoft 365 作用中使用者報告
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: fc1cf1d0-cd84-43fd-adb7-a4c4dfa8112d
description: 瞭解如何使用 Microsoft 365 系統管理中心中的「Microsoft 365 報告」儀表板來取得作用中使用者報告，並找出使用的產品授權數目。
ms.openlocfilehash: d127ddccd4944279052c628cbee9cc37dd3c8358
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391360"
---
# <a name="assess-the-microsoft-365-active-users-report"></a><span data-ttu-id="57a87-103">評估 Microsoft 365 作用中使用者報告</span><span class="sxs-lookup"><span data-stu-id="57a87-103">Assess the Microsoft 365 Active Users report</span></span>

<span data-ttu-id="57a87-104">[Microsoft 365 **報告**] 儀表板會顯示您組織中產品的活動概況。</span><span class="sxs-lookup"><span data-stu-id="57a87-104">The Microsoft 365 **Reports** dashboard shows you the activity overview across the products in your organization.</span></span> <span data-ttu-id="57a87-105">此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。</span><span class="sxs-lookup"><span data-stu-id="57a87-105">It enables you to drill in to individual product level reports to give you more granular insight about the activities within each product.</span></span> <span data-ttu-id="57a87-106">請參閱[報告概觀主題](activity-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="57a87-106">Check out [the Reports overview topic](activity-reports.md).</span></span>
  
<span data-ttu-id="57a87-107">例如，您可以使用 [作用中的 **使用者** ] 報告，找出組織中個人使用的產品授權數目，並深入瞭解使用者使用哪些產品的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="57a87-107">For example, you can use the **Active Users** report to find out how many product licenses are being used by individuals in your organization, and drill down for information about which users are using what products.</span></span> <span data-ttu-id="57a87-108">這份報告可協助系統管理員識別使用率低的產品或可能需要其他訓練或資訊的使用者。</span><span class="sxs-lookup"><span data-stu-id="57a87-108">This report can help administrators identify underutilized products or users that might need additional training or information.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="57a87-109">您必須是全域系統管理員、全域讀取者或報告讀取者 Microsoft 365 或 Exchange、SharePoint、Teams 服務、Teams 通訊或商務用 Skype 管理員查看報告。</span><span class="sxs-lookup"><span data-stu-id="57a87-109">You must be a global administrator, global reader or reports reader in Microsoft 365 or an Exchange, SharePoint, Teams Service, Teams Communications, or Skype for Business administrator to see reports.</span></span>  

## <a name="how-to-get-to-the-active-users-report"></a><span data-ttu-id="57a87-110">如何取得作用中的使用者報告</span><span class="sxs-lookup"><span data-stu-id="57a87-110">How to get to the Active Users report</span></span>

1. <span data-ttu-id="57a87-111">在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="57a87-111">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
2. <span data-ttu-id="57a87-112">在 [儀表板] 主頁上，按一下 [作用中的使用者-Microsoft 365 服務] 上的 [**查看其他**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="57a87-112">From the dashboard homepage, click on the **View more** button on the Active users - Microsoft 365 Services card.</span></span>

## <a name="interpret-the-active-users-report"></a><span data-ttu-id="57a87-113">解讀作用中的使用者報告</span><span class="sxs-lookup"><span data-stu-id="57a87-113">Interpret the Active Users report</span></span>

<span data-ttu-id="57a87-114">您可以選擇 [作用中的 **使用者**] 索引標籤，在 Office 365 報告中查看作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="57a87-114">You can view active users in the Office 365 report by choosing the **Active users** tab.</span></span><br/><span data-ttu-id="57a87-115">![Microsoft 365 報告-Microsoft Office 365 作用中的使用者。](../../media/56fe2e54-76ad-49e5-886f-1344c2697258.png)</span><span class="sxs-lookup"><span data-stu-id="57a87-115">![Microsoft 365 reports - Microsoft Office 365 active users.](../../media/56fe2e54-76ad-49e5-886f-1344c2697258.png)</span></span>

- <span data-ttu-id="57a87-116">[作用中的使用者] 報告可讓您檢視過去 7 天、30 天、90 天或 180 天的趨勢。</span><span class="sxs-lookup"><span data-stu-id="57a87-116">The Active Users report can be viewed for trends over the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="57a87-117">不過，如果您在報告中查看某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。</span><span class="sxs-lookup"><span data-stu-id="57a87-117">However, if you view a particular day in the report, the table (7) will show data for up to 28 days from the current date (not the date the report was generated).</span></span>

- <span data-ttu-id="57a87-118">每個報告中的資料通常會涵蓋過去24到48小時。</span><span class="sxs-lookup"><span data-stu-id="57a87-118">The data in each report usually covers up to the last 24 to 48 hours.</span></span>

- <span data-ttu-id="57a87-119">[使用者] 圖表會向您顯示以產品分隔的報表期間中每日作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="57a87-119">The Users chart shows you daily active users in the reporting period separated by product.</span></span>
<span data-ttu-id="57a87-120">[活動] 圖表會顯示以產品分隔報告期間中的每日活動計數。</span><span class="sxs-lookup"><span data-stu-id="57a87-120">The Activity chart shows you daily activity count in the reporting period separated by product.</span></span>
<span data-ttu-id="57a87-121">[服務] 圖表會顯示活動類型和服務的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="57a87-121">The Services chart shows you count of users by activity type and Service.</span></span>

- <span data-ttu-id="57a87-122">在 [使用者] 圖表上，X 軸會顯示所選的報表時間期間，y 軸會顯示每日作用中的使用者，並依授權類型以色彩編碼。</span><span class="sxs-lookup"><span data-stu-id="57a87-122">On the Users chart, the x axis shows the selected reporting time period and the y axis displays the daily active users separated and color coded by license type.</span></span>
<span data-ttu-id="57a87-123">在 [活動] 圖表上，X 軸會顯示所選的報表時間期間，y 軸會顯示每日活動計數和依授權類型編碼的色彩。</span><span class="sxs-lookup"><span data-stu-id="57a87-123">On the Activity chart, the x axis shows the selected reporting time period and the y axis displays the daily activity count separated and color coded by license type.</span></span>
<span data-ttu-id="57a87-124">在 [服務] 活動圖表上，X 軸會顯示在指定的時間週期中使用者啟用的各個服務，而 Y 軸是依活動狀態顯示使用者數目，以不同顏色表示不同的活動狀態。</span><span class="sxs-lookup"><span data-stu-id="57a87-124">On the Services activity chart, the X axis displays the individual services your users are enabled for in the given time period and the Y axis is the Count of users by activity status, color coded by activity status.</span></span>

- <span data-ttu-id="57a87-125">您可以選取圖例中的專案，以篩選您在圖表上看到的數列。</span><span class="sxs-lookup"><span data-stu-id="57a87-125">You can filter the series you see on the chart by selecting an item in the legend.</span></span> <span data-ttu-id="57a87-126">變更此選取項目並不會變更格線資料表中的資訊。</span><span class="sxs-lookup"><span data-stu-id="57a87-126">Changing this selection doesn't change the info in the grid table.</span></span>

- <span data-ttu-id="57a87-127">您也可以選取 [匯出] 連結，將報表資料匯出至 Excel .csv 檔案中。</span><span class="sxs-lookup"><span data-stu-id="57a87-127">You can also export the report data into an Excel .csv file, by selecting the Export link.</span></span> <span data-ttu-id="57a87-128">這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。</span><span class="sxs-lookup"><span data-stu-id="57a87-128">This exports data of all users and enables you to do simple sorting and filtering for further analysis.</span></span> <span data-ttu-id="57a87-129">如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。</span><span class="sxs-lookup"><span data-stu-id="57a87-129">If you have less than 2000 users, you can sort and filter within the table in the report itself.</span></span> <span data-ttu-id="57a87-130">如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。</span><span class="sxs-lookup"><span data-stu-id="57a87-130">If you have more than 2000 users, in order to filter and sort, you will need to export the data.</span></span>

- <span data-ttu-id="57a87-131">您可以使用欄控制項來變更格線表格中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="57a87-131">You can change what information is displayed in the grid table with column controls.</span></span>
<span data-ttu-id="57a87-132">如果您的訂閱是由世紀運作，您就不會看到 Yammer。</span><span class="sxs-lookup"><span data-stu-id="57a87-132">If your subscription is operated by 21Vianet, then you will not see Yammer.</span></span>



<span data-ttu-id="57a87-133">如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="57a87-133">If your organization's policies prevents you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports.</span></span> <span data-ttu-id="57a87-134">請參閱 [Microsoft 365 系統管理中心中活動報告](activity-reports.md)中的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="57a87-134">Check out the **How do I hide user level details?** section in [Activity Reports in the Microsoft 365 admin center](activity-reports.md).</span></span>  
