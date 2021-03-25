---
title: 裝置時程表中的技術
description: 瞭解 Microsoft Defender for Endpoint 中的裝置時程表
keywords: 裝置時程表、端點、MITRE、MITRE ATT&CK、技術、戰術
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185464"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="ac760-104">裝置時程表中的技術</span><span class="sxs-lookup"><span data-stu-id="ac760-104">Techniques in the device timeline</span></span>


<span data-ttu-id="ac760-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ac760-105">**Applies to:**</span></span>
- [<span data-ttu-id="ac760-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ac760-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="ac760-107">您可以透過分析特定裝置上發生的事件，在調查中取得更深入的洞察力。</span><span class="sxs-lookup"><span data-stu-id="ac760-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="ac760-108">首先，從 [ [裝置] 清單](machines-view-overview.md)中選取感興趣的裝置。</span><span class="sxs-lookup"><span data-stu-id="ac760-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="ac760-109">在 [裝置] 頁面上，您可以選取 [ **時程表** ] 索引標籤，以查看裝置上發生的所有事件。</span><span class="sxs-lookup"><span data-stu-id="ac760-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="ac760-110">瞭解時程表中的技巧</span><span class="sxs-lookup"><span data-stu-id="ac760-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="ac760-111">有些資訊與公開預覽中的 prereleased 產品功能有關，在正式發行之前，可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="ac760-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ac760-112">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="ac760-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ac760-113">在 Microsoft Defender for Endpoint 中， **技術** 是在事件時程表中的其他資料類型。</span><span class="sxs-lookup"><span data-stu-id="ac760-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="ac760-114">技術可深入瞭解與 [MITRE ATT&CK](https://attack.mitre.org/) 技術或子技巧相關聯的活動。</span><span class="sxs-lookup"><span data-stu-id="ac760-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="ac760-115">這項功能可協助分析員瞭解裝置上所觀察到的活動，以簡化調查體驗。</span><span class="sxs-lookup"><span data-stu-id="ac760-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="ac760-116">分析師可以決定進一步調查。</span><span class="sxs-lookup"><span data-stu-id="ac760-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="ac760-117">針對公開預覽，在查看裝置的時程表時，預設會提供技術，並與事件一起顯示。</span><span class="sxs-lookup"><span data-stu-id="ac760-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![裝置時程表螢幕擷取畫面中的技巧](images/device-timeline-2.png)

<span data-ttu-id="ac760-119">技術會以粗體文字反白顯示，左側會顯示藍色圖示。</span><span class="sxs-lookup"><span data-stu-id="ac760-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="ac760-120">對應的 MITRE ATT&CK 識別碼和技術名稱也會顯示為 [其他資訊] 底下的標記。</span><span class="sxs-lookup"><span data-stu-id="ac760-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="ac760-121">搜尋和匯出選項也可用於技術。</span><span class="sxs-lookup"><span data-stu-id="ac760-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="ac760-122">使用側邊窗格調查</span><span class="sxs-lookup"><span data-stu-id="ac760-122">Investigate using the side pane</span></span>

<span data-ttu-id="ac760-123">選取技術以開啟其對應的側邊窗格。</span><span class="sxs-lookup"><span data-stu-id="ac760-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="ac760-124">您可以在這裡看到其他資訊和洞察力，如相關的 ATT&CK 技術、戰術及描述。</span><span class="sxs-lookup"><span data-stu-id="ac760-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="ac760-125">選取「相關的 ATT&CK 技術」頁面 *，可在* 此找到相關的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ac760-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="ac760-126">當您在右側看到藍色圖示時，您可以複製實體的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ac760-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="ac760-127">例如，若要複製相關檔案的 SHA1，請選取 [藍色] 頁面圖示。</span><span class="sxs-lookup"><span data-stu-id="ac760-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![複製實體詳細資料](images/techniques-side-pane-clickable.png)

<span data-ttu-id="ac760-129">您可以對命令列執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="ac760-129">You can do the same for command lines.</span></span>

![複製命令列](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="ac760-131">調查相關事件</span><span class="sxs-lookup"><span data-stu-id="ac760-131">Investigate related events</span></span>

<span data-ttu-id="ac760-132">若要使用 [高級搜尋](advanced-hunting-overview.md) 來尋找與所選技術相關的事件，請選取 [ **尋找相關的事件**]。</span><span class="sxs-lookup"><span data-stu-id="ac760-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="ac760-133">這會導致「高級搜尋」頁面具有查詢，以尋找與技術相關的事件。</span><span class="sxs-lookup"><span data-stu-id="ac760-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![尋找相關的事件](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="ac760-135">使用 [技術] 側窗格中的 [ **尋找相關事件** ] 按鈕進行查詢，會顯示與所識別之技術相關的所有事件，但不會在查詢結果中包含此技術本身。</span><span class="sxs-lookup"><span data-stu-id="ac760-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="ac760-136">自訂裝置時程表</span><span class="sxs-lookup"><span data-stu-id="ac760-136">Customize your device timeline</span></span>

<span data-ttu-id="ac760-137">在裝置時程表的右上方，您可以選擇日期範圍來限制時程表中的事件及技術數目。</span><span class="sxs-lookup"><span data-stu-id="ac760-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="ac760-138">您可以自訂要公開的資料行。</span><span class="sxs-lookup"><span data-stu-id="ac760-138">You can customize which columns to expose.</span></span> <span data-ttu-id="ac760-139">您也可以依資料類型或事件群組，篩選已標記的事件。</span><span class="sxs-lookup"><span data-stu-id="ac760-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="ac760-140">選擇要公開的資料行</span><span class="sxs-lookup"><span data-stu-id="ac760-140">Choose columns to expose</span></span>
<span data-ttu-id="ac760-141">您可以選取 [ **選擇欄** ] 按鈕，以選擇要在時程表中公開的欄。</span><span class="sxs-lookup"><span data-stu-id="ac760-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![自訂欄](images/filter-customize-columns.png)

<span data-ttu-id="ac760-143">您可以從這裡選擇要包含的資訊集。</span><span class="sxs-lookup"><span data-stu-id="ac760-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="ac760-144">篩選只查看技術或事件</span><span class="sxs-lookup"><span data-stu-id="ac760-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="ac760-145">若只要查看事件或技術，請從裝置時程表選取 [ **篩選器** ]，然後選擇要查看的慣用資料類型。</span><span class="sxs-lookup"><span data-stu-id="ac760-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![篩選螢幕擷取畫面](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="ac760-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ac760-147">See also</span></span>
- [<span data-ttu-id="ac760-148">查看及組織裝置清單</span><span class="sxs-lookup"><span data-stu-id="ac760-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="ac760-149">Microsoft Defender for Endpoint 裝置的時間表事件旗標</span><span class="sxs-lookup"><span data-stu-id="ac760-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
