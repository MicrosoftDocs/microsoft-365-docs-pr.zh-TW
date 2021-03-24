---
title: 調查 Microsoft Defender for Endpoint 警示
description: 使用調查選項來取得有關警示的詳細資料、其意義，以及如何解決。
keywords: 調查，調查，裝置，裝置，警示佇列，儀表板，IP 位址，檔案，送出、提交、深入分析、時程表、搜尋、網域、URL、IP
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
ms.openlocfilehash: 498f2d83af6e2eb7fc56b232bafd9fc49d9d4fd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060111"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4ab39-104">調查 Microsoft Defender for Endpoint 中的警示</span><span class="sxs-lookup"><span data-stu-id="4ab39-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ab39-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4ab39-105">**Applies to:**</span></span>
- [<span data-ttu-id="4ab39-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4ab39-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4ab39-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ab39-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4ab39-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4ab39-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4ab39-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="4ab39-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="4ab39-110">調查影響網路的警示，瞭解其含義及解決方法。</span><span class="sxs-lookup"><span data-stu-id="4ab39-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="4ab39-111">選取 [警示] 佇列中的警示，以移至 [警示] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4ab39-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="4ab39-112">此視圖包含提醒標題、受影響的資產、詳細資料側窗格及警示案例。</span><span class="sxs-lookup"><span data-stu-id="4ab39-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="4ab39-113">在 [警示] 頁面中，選取 [警示案例] 樹狀目錄中的受影響資產或任何實體，以開始調查。</span><span class="sxs-lookup"><span data-stu-id="4ab39-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="4ab39-114">[詳細資料] 窗格會自動填入有關您所選取之專案的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4ab39-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="4ab39-115">若要查看您可以在這裡查看的資訊類型，請閱讀 [Microsoft Defender For Endpoint 中的審閱警示](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts)。</span><span class="sxs-lookup"><span data-stu-id="4ab39-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="4ab39-116">使用警示案例調查</span><span class="sxs-lookup"><span data-stu-id="4ab39-116">Investigate using the alert story</span></span>

<span data-ttu-id="4ab39-117">警示案例會詳細說明觸發警示的原因、之前與之後發生的相關事件，以及其他相關實體。</span><span class="sxs-lookup"><span data-stu-id="4ab39-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="4ab39-118">實體是可按一下的，而每個非警示的實體都會使用該實體的卡片右側的展開圖示展開。</span><span class="sxs-lookup"><span data-stu-id="4ab39-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="4ab39-119">焦點中的實體會由該實體卡片左側的藍色點線表示，而且標題中的警示會先開始。</span><span class="sxs-lookup"><span data-stu-id="4ab39-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="4ab39-120">展開實體以快速查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4ab39-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="4ab39-121">選取實體會將詳細資料窗格的內容切換至此實體，並可讓您複查進一步的資訊，以及管理該實體。</span><span class="sxs-lookup"><span data-stu-id="4ab39-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="4ab39-122">在實體卡片 *右邊選取 [...]* ，會顯示該實體所有可用的動作。</span><span class="sxs-lookup"><span data-stu-id="4ab39-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="4ab39-123">當該實體處於焦點中時，這些相同動作會出現在詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="4ab39-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="4ab39-124">「警示案例」區段中可能會包含一個以上的警示，在您所選取的警示之前或之後，會顯示與相同執行樹狀目錄相關的其他警示。</span><span class="sxs-lookup"><span data-stu-id="4ab39-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![警示案例的範例，具有專注的警示和部分擴充的卡片](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="4ab39-126">從詳細資料窗格採取動作</span><span class="sxs-lookup"><span data-stu-id="4ab39-126">Take action from the details pane</span></span>

<span data-ttu-id="4ab39-127">當您選取相關實體時，詳細資料窗格會變更，以顯示所選實體類型的相關資訊，並提供歷史資訊，以直接從警示頁面對此實體 **採取動作** 。</span><span class="sxs-lookup"><span data-stu-id="4ab39-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="4ab39-128">完成調查後，請回到您已開始的警示，將警示的狀態標示為 [ **已解決** ]，然後將其歸類為 **False 警示** 或 **True 警示**。</span><span class="sxs-lookup"><span data-stu-id="4ab39-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="4ab39-129">分類提醒可協助調整這項功能，以提供更真實的警示及不太虛假的警示。</span><span class="sxs-lookup"><span data-stu-id="4ab39-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="4ab39-130">如果您將其歸類為 true 警示，您也可以選取判斷，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="4ab39-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![詳細資料窗格中含有已解析之警示和確定下拉式展開功能的程式碼片段](images/alert-details-resolved-true.png)

<span data-ttu-id="4ab39-132">如果您遇到的是與企業營運相關的預警，請建立抑制規則，以避免未來出現這種類型的警示。</span><span class="sxs-lookup"><span data-stu-id="4ab39-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![在詳細資料窗格中高亮顯示隱藏規則的動作和分類](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="4ab39-134">如果您遇到上述任何問題，請使用 🙂 按鈕提供意見反應或開啟支援票證。</span><span class="sxs-lookup"><span data-stu-id="4ab39-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4ab39-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="4ab39-135">Related topics</span></span>
- [<span data-ttu-id="4ab39-136">查看和組織 Microsoft Defender for Endpoint 警示佇列</span><span class="sxs-lookup"><span data-stu-id="4ab39-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="4ab39-137">管理 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="4ab39-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="4ab39-138">調查與 Defender for Endpoint alert 相關聯的檔案</span><span class="sxs-lookup"><span data-stu-id="4ab39-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- <span data-ttu-id="4ab39-139">[調查 [Defender for Endpoint Devices] 清單中的裝置](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="4ab39-139">[Investigate devices in the Defender for Endpoint Devices list](investigate-machines.md)</span></span>
- [<span data-ttu-id="4ab39-140">調查與 Defender for Endpoint alert 相關聯的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="4ab39-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="4ab39-141">調查與 Defender for Endpoint alert 相關聯的網域</span><span class="sxs-lookup"><span data-stu-id="4ab39-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="4ab39-142">調查 Endpoint for Endpoint 中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="4ab39-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


