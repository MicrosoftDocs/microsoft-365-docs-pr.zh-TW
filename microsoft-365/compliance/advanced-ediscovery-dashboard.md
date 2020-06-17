---
title: 審閱集的高級 eDiscovery 儀表板
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用高級 eDiscovery 儀表板做為複查集，以快速分析您的主體，以找出可協助您開發考核策略的趨勢或關鍵統計資料。
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741694"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a><span data-ttu-id="d344e-103">審閱集的高級 eDiscovery 儀表板</span><span class="sxs-lookup"><span data-stu-id="d344e-103">Advanced eDiscovery dashboard for review sets</span></span>

<span data-ttu-id="d344e-104">在高級 eDiscovery 中的某些案例中，您可能需要檢查大量的檔和電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="d344e-104">For some cases in Advanced eDiscovery, you may have a large volume of documents and email messages that need to be reviewed.</span></span> <span data-ttu-id="d344e-105">開始審查程式之前，您可能會想要快速分析您的主體，以找出可協助您開發考核策略的趨勢或重要統計資料。</span><span class="sxs-lookup"><span data-stu-id="d344e-105">Before you start the review process, you may want to quickly analyze your corpus to identify trends or key statistics that will help you develop your review strategy.</span></span> <span data-ttu-id="d344e-106">若要這麼做，您可以使用 Advanced eDiscovery 儀表板進行審核，以快速分析您的主體。</span><span class="sxs-lookup"><span data-stu-id="d344e-106">To do this, you can use the Advanced eDiscovery dashboard for review sets to quickly analyze your corpus.</span></span>

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a><span data-ttu-id="d344e-107">步驟1：在審閱集儀表板上建立小工具</span><span class="sxs-lookup"><span data-stu-id="d344e-107">Step 1: Create a widget on the review set dashboard</span></span>

1. <span data-ttu-id="d344e-108">在安全性 & 規範中心內，移至**eDiscovery > Advanced ediscovery** ，以顯示組織中案例的清單。</span><span class="sxs-lookup"><span data-stu-id="d344e-108">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="d344e-109">選取現有的案例。</span><span class="sxs-lookup"><span data-stu-id="d344e-109">Select an existing case.</span></span>
  
3. <span data-ttu-id="d344e-110">按一下 [**複查集**] 索引標籤，然後選取一種複查集。</span><span class="sxs-lookup"><span data-stu-id="d344e-110">Click the **Review Set** tab, and then select a review set.</span></span>
  
4. <span data-ttu-id="d344e-111">在 [**個別結果**] 下拉式清單中，按一下 [**搜尋設定檔視圖**]。</span><span class="sxs-lookup"><span data-stu-id="d344e-111">In the **Individual results** dropdown list, click **Search profile view**.</span></span> 

   ![DashbordPivot](../media/dashboardpivot.png)

   <span data-ttu-id="d344e-113">隨即會顯示 [**搜尋設定檔視圖**] 頁面。第一次顯示此頁面時，會顯示三個預設構件。</span><span class="sxs-lookup"><span data-stu-id="d344e-113">The **Search profile view** page is displayed; the first time you display this page, three default widgets are displayed.</span></span>

   ![儀表板](../media/dashboardonly.png)
  
5. <span data-ttu-id="d344e-115">按一下**新的小工具**，然後選取下列其中一個專案：</span><span class="sxs-lookup"><span data-stu-id="d344e-115">Click the **New  widget** and then select one of the following items:</span></span>

   ![新增小工具下拉式清單](../media/NewWidgetDropdownBox.png)

   - <span data-ttu-id="d344e-117">**從文件庫選擇：** 會顯示小元件的預設文件庫。</span><span class="sxs-lookup"><span data-stu-id="d344e-117">**Choose from library:** Displays a default library of widgets.</span></span> <span data-ttu-id="d344e-118">按一下一個小工具，然後按一下 [**新增**]，將其新增至 [**搜尋設定檔視圖**] 頁面上的小工具。</span><span class="sxs-lookup"><span data-stu-id="d344e-118">You click a widget and then click **Add** to add it to the widgets on the **Search profile view** page.</span></span>
  
   - <span data-ttu-id="d344e-119">**建立自訂構件：** 顯示可讓您用來設定自訂構件的飛彈出頁面。</span><span class="sxs-lookup"><span data-stu-id="d344e-119">**Create custom widget:** Displays a flyout page that you can use to set up a custom widget.</span></span> 

6. <span data-ttu-id="d344e-120">若要建立自訂的小工具，請在 [**新增小**工具] 飛入頁面上執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d344e-120">To create a custom widget, do the following on the **Add widget** flyout page:</span></span>

   ![建立小工具](../media/addwidget.png)

    <span data-ttu-id="d344e-122">a.</span><span class="sxs-lookup"><span data-stu-id="d344e-122">a.</span></span> <span data-ttu-id="d344e-123">輸入構件的名稱，它會顯示在 [widget] 標題列中。</span><span class="sxs-lookup"><span data-stu-id="d344e-123">Type a name for the widget, which is displayed in the widget title bar.</span></span> <span data-ttu-id="d344e-124">需要命名小工具，但識別小工具資料有説明。</span><span class="sxs-lookup"><span data-stu-id="d344e-124">Naming a widget is required, but it's helpful to identify the widget data.</span></span>

    <span data-ttu-id="d344e-125">b.</span><span class="sxs-lookup"><span data-stu-id="d344e-125">b.</span></span> <span data-ttu-id="d344e-126">在 [**選擇樞紐分析表**] 下拉式清單中選取要用於小工具資料的屬性。</span><span class="sxs-lookup"><span data-stu-id="d344e-126">Select a property in the **Choose pivot** dropdown list that will be used for the widget data.</span></span> <span data-ttu-id="d344e-127">在此清單中的專案是審閱集內專案的可搜尋屬性。</span><span class="sxs-lookup"><span data-stu-id="d344e-127">The items in this list are the searchable properties for the items in the review set.</span></span> <span data-ttu-id="d344e-128">如需這些屬性的說明，請參閱[Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d344e-128">For a description of these properties, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="d344e-129">小工具的 pivot 選項會列在本主題的可搜尋**欄位名稱**欄中。</span><span class="sxs-lookup"><span data-stu-id="d344e-129">The pivot options for the widget are listed in the **Searchable field name** column in this topic.</span></span>

    <span data-ttu-id="d344e-130">c.</span><span class="sxs-lookup"><span data-stu-id="d344e-130">c.</span></span> <span data-ttu-id="d344e-131">選取圖表類型以顯示選取的 pivot 屬性中的資料。</span><span class="sxs-lookup"><span data-stu-id="d344e-131">Select a chart type to display the data from the selected pivot property.</span></span>

  6. <span data-ttu-id="d344e-132">按一下 [**新增**] 以建立自訂構件，並將其顯示在 [**搜尋設定檔視圖**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="d344e-132">Click **Add** to create the custom widget and display it on the **Search profile view** page.</span></span>

## <a name="step-2-create-a-review-set-search-query"></a><span data-ttu-id="d344e-133">步驟2：建立複查集搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="d344e-133">Step 2: Create a review set search query</span></span>

1. <span data-ttu-id="d344e-134">按一下小工具標題列中的 [ **...** ]，然後按一下 [套用**條件**]。</span><span class="sxs-lookup"><span data-stu-id="d344e-134">Click **...** in the widget title bar, and then click **Apply condition**.</span></span>

   ![儀表板](../media/searchprofilehome.png)

2. <span data-ttu-id="d344e-136">在飛入頁面上，按一下 [widget 鍵] 或 [小小工具] 圖表上的元素，以建立篩選。</span><span class="sxs-lookup"><span data-stu-id="d344e-136">On the flyout page, click an element on the widget key or widget chart to create a filter.</span></span>

   ![CreateFilter](../media/applyconditionfilter.png)

3. <span data-ttu-id="d344e-138">對其他小小小元件重複步驟1-2。</span><span class="sxs-lookup"><span data-stu-id="d344e-138">Repeat steps 1-2 for other widgets multiple widgets.</span></span> 

4. <span data-ttu-id="d344e-139">當您完成時，按一下 [**另存**新檔]，將您的條件儲存為審閱集的新搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="d344e-139">When you're done, click **Save as query** to save your conditions as a new search query for the review set.</span></span>

   ![查詢](../media/savequery.png)

5. <span data-ttu-id="d344e-141">關閉**搜尋設定檔視圖**，以回到搜尋結果檢視。</span><span class="sxs-lookup"><span data-stu-id="d344e-141">Close the **Search profile view** to return to the search results view.</span></span>

   <span data-ttu-id="d344e-142">如果您已建立任何視覺篩選器，則產生的查詢會套用至所顯示的搜尋結果，而您在步驟4中儲存的搜尋查詢會顯示在 [**已儲存的查詢**] 底下。</span><span class="sxs-lookup"><span data-stu-id="d344e-142">If you have created any visual filters, the resulting query is applied to the search results that are displayed, and the search query that you saved in step 4 is displayed under **Saved queries**.</span></span> <span data-ttu-id="d344e-143">如需複查集合查詢的詳細資訊，請參閱[在審閱集中查詢資料](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d344e-143">For more information about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>
